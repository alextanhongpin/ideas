## Technology Stacks

-	Containers. Everything will be Docker-based – for now we will utilize AWS ECS before moving to AWS EKS (currently still in Preview). Migration should be seamless – the goal is to encourage developers to move everything to Docker.
-	JSON API. To align with the API Standards, we will model all our APIs based on the JSON API Specification. 

Reference: http://jsonapi.org/

-	JSON Schema/Contract Pact Testing. For validation, we prefer JSON Schema over Swagger, since Swagger only models the HTTP REST APIs – not all services will be exposed through HTTP, so Swagger can be restricting.

Reference: http://json-schema.org/

-	RPC. For internal services (System/Process APIs), it is recommended to use RPC for communication. Only services that are client-facing should be exposed as HTTP Endpoints.

Reference: https://blog.twitch.tv/twirp-a-sweet-new-rpc-framework-for-go-5f2febbf35f

-	Three-Layered Approach. Identify where the new services will be located in this three-layer architecture. Consist of System APIs, Process APIs and Experience APIs. In the Process API layer, it will contain separate logic for JobsDB and JobStreet Services, which will then be orchestrated in the Experience API (client-facing end). 

Reference: https://blogs.mulesoft.com/dev/api-dev/apis-great-architecture/

-	Service Discovery. We need a way to allow services to be discovered easily. Currently there are no official tool available on AWS, should look into Consul.
-	SLA. SLA is important – more important is how do we measure them and make them visible. Also, all information about services (deployment time, frequency etc) should be made transparent and align with the Service Portfolio initiatives.
-	API Lean Canvas. For teams that are requesting for new APIs, they can fill in a simple contract so that we can act accordingly. 

Reference: https://nordicapis.com/api-model-canvas-developer-experience-is-a-key-ingredient-of-quality-apis/

-	Event-Driven. All (relevant) logs data should be persisted in S3 for example. This data should be utilized (analytics, dashboards), not just kept. This should align with Data Team’s initiatives.

Overall, 80% of our work should be mainly exploitation (making use of existing standards, best practices) and the remaining 20% for exploration (researching new technologies, methodologies). It’s important that mature code be separated from unproven/untested implementations.


## API Lean Canvas

```
I’m sharing two links here that describes the API Model Canvas that was mentioned earlier:

1. https://nordicapis.com/api-model-canvas-developer-experience-is-a-key-ingredient-of-quality-apis/
2. http://www.apiacademy.co/tag/microservices/

We will definitely be getting ad-hoc requests from different team for APIs, and without a systematic approach, we might end up going in circles.

Therefore, we should be more specific on how we are going to handle the requests from other team. A suggestion would be to use the existing API Model Canvas, and customise it based on our needs. 

Here are some thoughts on things that we can add-on:

- The owner of the service, and the team using it
- Overview on what the services does, and who can access it
- Channels (by Country?)
- Data Storage (Which databases are we accessing/creating)
- Analytics (A simple overview on the relevant metrics that can be obtained from the services, which will be feed back to Roger’s centralised data mart)
- Language/Technology implementation - This will address the technology road map that we discussed previously.

Of course, this is not an enforcement, merely a suggestion.
```
