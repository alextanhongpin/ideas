## Root or Health endpoint

The root endpoint (`/`) may contain useful information. For example:

```javascript
{
  "deployed_at": "<RFC3339_DATE>",
  "uptime": "1h30m", // Uptime of the application in readable time format.
  "build_at": "<BUILD_DATE_FOR_THE_CONTAINER>", // The build date of the container/server to track how long the application has been there.
  "version": "<SHORT_GIT_HASH_VERSION>", // Short git hash, to easily find the commit history
  "semver": "1.0.0-beta", // The production version based on semver
  "team": "", // Team name
  "domain": "", // The domain of the microservice. User that opens this endpoint might not know what this server is for.
  "deployed_by": "john.doe@mail.com", // Probably not a good idea since there's an attack possibility.
  "email": "",
  "website": "",
  "environment": "kubernetes",
  "server_name": "johny_english", // Random name for checking logs
  "sprint": "",
  "sprint_version": "", // Fun identifier to track which sprint progress this is actually completed
  "target_stop": "", // Target stop date - can be used to kill the application once the target is completed
  "feature": "", // A/B Testing identifier. 
  "feature_score": "", // The score for the current tested A/B feature. We may, for e.g. deploy two instances that are load balanced with different features.
}
```

The `git_commit` is useful for:
- checking what is the last deployed version
- when there are bugs, it's easy to trace which commit
- can integrate with CI auto-deployment. If the version matches the current git, do not need to deploy

The `uptime` gives indication on:
- how long the server is up
- when did it restart? (compare with the build date or deployed at date). should probably find a way to log the number of restarts
- when the server should be brought down - if it's been up for too long, there are chances that the devs lose visibility on the service. Hence, the service should be brought down for inspection/upgrade/value definition. There's no point putting a server that no one uses! The value can be obtained through request metrics and so on.

## Health endpoint naming

`/health`, or `/_health`.

## JSON API/JSON Schema

To ease validation of large json schema, and also to standardize response type. 

## Versioning

```
/apis/v1/resources
```

The payload may change. What if we hash the payload with sha, and return them as version in the api response?

```
{
  "data": {},
  "version": "x0dsak12"
}
```

That way, the client can always cache the api response on the cient side, and make a call to compare if any of the values changed. One idea is just to perform hashing with SHA256, and take the first 6 characters as identifier:

```go
package main

import (
	"crypto/sha256"
	"encoding/json"
	"fmt"
)

type ResponseV2 struct {
	Name string `json:"name"`
	Age  int    `json:"age"`
}

type ResponseV1 struct {
	Name string
	Age  int
}

func main() {
	v1, _ := json.Marshal(ResponseV1{"hello", 1})
	h1 := sha256.New()
	h1.Write(v1)
	fmt.Printf("%x\n", h1.Sum(nil))

	v2, _ := json.Marshal(ResponseV2{"hello", 1})
	h2 := sha256.New()
	h2.Write(v2)
	fmt.Printf("%x\n", h2.Sum(nil))

	v3, _ := json.Marshal(ResponseV2{"world", 1})
	h3 := sha256.New()
	h3.Write(v3)
	fmt.Printf("% x\n", h3.Sum(nil))

	v4, _ := json.Marshal(ResponseV2{"world", 1})
	h4 := sha256.New()
	h4.Write(v4)
	fmt.Printf("% x\n", h4.Sum(nil))
}
```


## Context Logging

There are many ways to tie different part of the system together - and they are probably overlapping in roles and resposibilities. For example, it is possible to perform "tracing" through context-logging (adding a correlation-id or request-id and passing them down to other functions that calls it), opentracing with jaeger, metrics collection with prometheus or both of them with opencensus.

Some of the benefits includes:
- observability (knows what happen, and why)
- works well with auto-scaling application (by logging the hostname or unique identifier id, it's possible to trace which instance is having error)
- can trace bottleneck (by knowing where is the slowest path of the system). Remember, your service is only as fast as the slowest path of the system.
- can debug used/unused endpoints (though the test coverage should cover this, nevertheless this is useful when you deal with deprecated endpoints)
- aside from identifying internal paths (chain methods/services/calls between different domain services), it can also be used to detect external paths (http requests, rpc calls etc). This is useful again to identify which external calls are made.
- the request id can be passed in the JSON response body for the client to trace which requests is causing the error. They can then contact support with the request_id that when they encounter an error.
- detect attacks/compromised endpoints/fraud/abuse of privileges
- allow one to respond to events (logging data is just the first step)

## Logging request/response

It might be too much, but sometimes it is useful to log all the request/response of the application. 


## What to log?

TODO: Consolidate the practices

- date and time: timestamp of the event
- event name: the name of the event
- method/function: the method or function name that is called, or maybe the controller class
- args: The arguments that are passed as a request, or response that is being returned
- service name: the name of the service being called
- hostname: the host of the app
- request id: unique tracable request id
- external/internal request: http/uri or client name/metadata
- ip address: to avoid DDoS
- user-agent: to identify the caller, and which user-agent is having issue
- http status code - the error code makes filtering the logs easier
- context: the context of the call
- entrypoint: the first entrypoint of the logs - to enable tracing
- paths: the paths is just a concatenated string of the path taken by the application throughout the requests lifecycle - useful to detect abnormalities.
- the application id or git SHA
- information of the client/user issuing the request
- the function name and line number that the log line came from
- the server's host name
- the structure of the logs (whether it's JSON or Key-Value pairs) does not matter much, except for compatibilty with the tools to monitor/filter the logs

What else to log:
- log all validation failures
- log all authentication attempts, especially failures
- log all access control failures
- log all apparent temperting events or unexpected changes to state data
- log all attempts to connect with invalid or expired session tokens
- log all system exceptions

## Sensitive Data

- personal identifiable data. Data such as Social Security Number, names (full name or nickname), date of birth, addresses, user generated data such as email, or combination of data (gender, age etc) may leak information.
- phone number/email
- health data
- financial data (bank names, credit card number)
- passwords
- ip addresses 
- private keys
- access keys

remember to:
- keep sensitive data out of urls (`/user/<email>`)
- keep sensitive data out of logs
- have automated pipeline that filters/monitors for such sensitive information


## Challenges in logging

What developers do:
```
console.log('error:', err.message)
```

This is a particularly useless log. When something happens, this log will not provide _value_. Instead, compare this:

- timestamp of the trusted sytem component, preferably UTC RFC3339
- severity rating for each event
- event name
- unique request id
- paths taken by the event
- identity of the account/user that caused the event
- source IP address associated with the request
- event outcome (success/failure)
- description of the event

There needs to be some sweet spot between noise and signal. Logging data that does not provide value might end up increasing the surface attack, and wasting resources/consuming space. There are several things to consider:

- how to access logs
- how to perform search/filter
- who can perform/access the logs
- storage growth requirements - what is the rate of change
- what happens when DDoS occurs (millions of exceptions in logs)
- data retention periods? 3 months/3 years?

The OWASP logging guide is a must see. Summarize your learning from there


## Protected APIs

There are several ways to protect the API from being accessed by unauthorized users. Let's take a look at how to handle it for public and private (admin) apis. 
- public, but require no auth: We can simply create an anonymous session to keep track of the calls from a public api. This is useful for analytics.
- public, but require auth: For read only, use an API key. This is useful to throttle the calls and for tracking analytics. For any update and delete operations, ensure that the user is provided a token separate from the read API token. Else, user can just reuse the read token to manipulate other people's data. The write token should be usable once only, and such makes the OTP token a good candidate. The token can only be generated on the server side, and is valid for the particular user. Note that this implementation is slightly stateful. We need to tie the session to the server in order to accomplish this. This means that the creation/updating of data can only be done on the webpage, and not through API.
- private. For eg, admin APIs or ops APIs where only internal user can update.


Separate read and write api. By default, read api should be more lenient (if the data is not sensitive etc). For write data, rate-limit it to prevent abuse. Better, prompt user to re-authenticate again in order to perform a write (if it's sensitive data, like user profile update etc). Rather than setting a time-limit only for the user to perform write, set a threshold limit too. E.g. an api key to write is only valid for the next 10 minutes and 5 writes (success and fail). 


## Returning error

When returning error response, it is better to be explicit. Ensure all fields are validated, and if the endpoint usually involves multiple steps (more steps, more risks of failure), then return the `request_id` that is passed through the context for logging as the `error_code`. This allows Ops to debug for issues by simple searching for the code in the logs management system. 

```json
{
	"error": "id is required",
	"error_code": "65903c20-04dc-4b78-9684-b2db93e81a2b"
}
```

When and when not to return the `error_code`?
- If it is a simple `GET` endpoint, do not return. It will only add to noise.
- If there are no logs using that `request_id`, do not return.
- If it is a complex step that requires many processes, with logging in between each steps, return the error code.

## Creating Ops Access

Most of the time, your apis needs to be accessed by the ops side to perform admin stuff (resetting password, updating resources information). Prepare a set of admin credentials, and use scopes in JWT to limit access.

There are several options for this:
1) passing credentials through env vars. Note that it's not safe to pass plaintext credentials through env vars. Always hash them (e.g. through md5). Then, in your application, just compare the hash of the credentials passed in with the ones set in the env variables. The crendentials would be mostly static most of the time, but can be updated through env vars.

```
# $ echo -n john:123456 | md5
ADMIN_CREDENTIALS=7a661e6b4faa9aa10a97b0f3374bf414
```

2) generating them through the application. It is possible to create dynamic config, and set a cron job to refresh the credentials daily. E.g. `generateCredentials()` method in the application will create a new login credentials at 12 am daily. The credentials will then be emailed/send through slack/mobile etc for users to use it.


## Blocker for Frontend

Often, the FE needs some API's to be fetched/posted, which the BE does not provide. It is useful to create a dumb echo endpoint that just accepts anything and return the same thing back to the FE. This way, the FE won't be block and can just replace the endpoint with actual calls when it is completed on the BE.


## Error messages

It's useful to return the correlation id (a.k.a `request_id`) in the error response, so that it can be send as a report from the client. Client can show a form to submit crash report with the given correlation id so that the developer can debug the errors caused by it.
```js
{
  "error": "date is required",
  "error_code": "uuid",
  "error_message": "based on localization"
}
```

Localization is difficult in this case. The error message should hence be generic, so that the client can parse it and handle it according to the localization on the client side.

The server can also returned the localized translated error message to the client, if the client sends the language information to the server, e.g. through the header `Accept-Language`. The server needs to handle the language if available, or defaults to english if not. Look into `i18n` and also `l10n` on how to make your application fits the different locale.

References:
- https://stackoverflow.com/questions/50986333/rest-api-request-with-language-and-region


## Pagination

- limit, offset
- cursor pagination (keyset pagination)

## Retries

Only retry when `error code > 500`. Display message if error code is `>400`.
