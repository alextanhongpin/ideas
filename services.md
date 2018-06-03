# Definition

Service takes a defined request, validates it, performs the business logic and returns the desired output.

Writing a *perfect* service can be daunting, since there are many ways requirements to fulfil. Here are some of the top requirements that I think every service will need.

- message queue
- design patterns
- configuration
  - environment variables
  - dynamic config
- store
- testing
  - integration
  - component
- performance
  - debugging
  - profiling
  - metrics gathering
- logging
  - audit logs
  - health check
  - distributed tracing
  - anomaly detection
  - report generation
- business logic
  - requirements
  - validation
  - scope
  - sla
- resiliency
  - failures
- cancellation/deadline/timeouts
- flexibility - how easy is it for your services to be consumed by different transports, be it REST, RPC/gRPC, msgpack, etc.? Or perhaps how easy it is to run it as a cron, or serverless function?
- modularity
- security
  - authentication
  - api gateway
  - rate-limiting
- deployability
  - frequency
  - features 
  - changelog
- portability - how easy is it to replicate this in different languages?
- service discovery
- scalability
  - load-balancing
  - horizontal scaling
  - vertical scaling - are your applications running out of memory or you need a larger instance to run a certain process? Before considering vertical scaling by adding more rams, memory, try profiling your application for performance bottleneck - it might save you a few hundred dollars.
- standards
  - json schema
  - json api
- documentation
  - swagger
  - protobuf IDL
  - auto-generating vs manual
  - creating a dependency graph
- versioning
  - semantic commits
  - changelog
- environment
  - development
- operations
  - ownership
  - cascading
  - Single Team Owned Service Architecture (STOSA)

## Testing
