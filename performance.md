## Performance for API

Microservices tends to have latency, especially when you have services that are calling other services. In order to identify the performance bottleneck, especially when dealing with high traffic api, we need to carry out benchmarking and adding monitoring.

The least we want to accomplish is:

- identify the bottleneck (the service that serve the slowest) so that it can be scaled accordingly
- generate reports on the health (req/s, downtime, etc) daily, weekly, monthly, yearly etc.
- rate-limit the endpoint
- secure endpoint with auth
- improve monitoring and observability
- able to come up with targetted monitoring (the performance reaches it's peak at 10:00 a.m. with xxx req/s) to carry out auto-scaling etc

Things that can be done:

- implement Open Tracing
- add monitoring through Prometheus
- add worker that generates report
- use machine learning to detect anomaly
