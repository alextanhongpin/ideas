## Root endpoint

The root endpoint (`/`) may contain useful information. For example:

```js
{
  "deployed_at": "<RFC3339_DATE>",
  "uptime": "1h30m", // Uptime of the application in readable time format.
  "build_at": <BUILD_DATE_FOR_THE_CONTAINER>", // The build date of the container/server to track how long the application has been there.
  "version": "<SHORT_GIT_HASH_VERSION>", // Short git hash, to easily find the commit history
  "semver": "1.0.0-beta", // The production version based on semver
  "team": "", // Team name
  "domain": "", // The domain of the microservice. User that opens this endpoint might not know what this server is for.
  "deployed_by": "john.doe@mail.com", // Probably not a good idea since there's an attack possibility.
  "email": "",
  "website": "",
  "environment": "kubernetes",
  "server_name": "johny_english", // Random name for checking logs
}
```

## Context Logging

There are many ways to tie different part of the system together - and they are probably overlapping in roles and resposibilities. For example, it is possible to perform "tracing" through context-logging (adding a correlation-id or request-id and passing them down to other functions that calls it), opentracing with jaeger, metrics collection with prometheus or both of them with opencensus.

## Logging request/response

It might be too much, but sometimes it is useful to log all the applications.
