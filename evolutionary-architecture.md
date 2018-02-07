# Evolutionary architecture

Setting up goals to create a more personalized architecture. 

## Alerting

Monitoring is for developers. As a non-technical person, I want to receive notifications on alerts that makes sense. 

- When a new services is deployed: `Your Spam Service is up! We will send you alerts if somethings goes wrong!`
- When an error occured: `Oops! New users are affected by your service! Turn it off now/revert to older version? XXX is currently on watch now! Contact him.`. (Feature toggle through Slack API)
- When someone is making changes: `XXX is deploying a new version to production! Say something!`
- At the end of the day/week/month/year: `Here's an overview on how your services are working!`. Display visualization on the metrics such as visits/usage/failures/uptime/SLAs etc.

## Intelligent APIs

Separate CRUD-based APIs from Algorithms APIs. Apply the concept of composition on APIs to make each of them reusable. Plain CRUD should only return the raw data - the preprocessing such as joining data from differet resources, mapping reference values, transforming data to different format should be done on a different level (the orchestration level). If necessary, the data that is flowing through should go through a centralized schema validator - it makes sense to validate data in one central place, the same idea applies for authorization/authentication.

## Reduce Workload

Apply algorithms like fair distributions/bin-packing to reduce the load. Also, use smart caching solutions that can reduce the number of calls to the server.

## Detecting anomalies

Using algorithms such as Random Forest to detect anomalies in the system and what creates it.

## Logging/Distributed Tracing

Logging could have been better. Also related to alerting - when the errors have hit certain threshold, it should send a notification to the users.

Identify the levels of errors we want to handle - Critical (when hit n amount), Warning (not an operation threat, but should alert the user too).

## SLAs

The SLAs of the service is like the KPI of the service. Design it in a way that it can be measured and reported back to the user.
Services that performs above the given SLAs should be used as an example, those that performs below the given SLAs should be rewritten and compared. 

The sum of all services SLAs is the architecture SLAs. The architecture SLAs indicates whether it is healthy or not. Components affecting the architecture SLAs should be removed.


