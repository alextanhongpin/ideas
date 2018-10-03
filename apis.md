## Root endpoint

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