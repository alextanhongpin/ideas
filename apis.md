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

## Logging request/response

It might be too much, but sometimes it is useful to log all the request/response of the application. 


