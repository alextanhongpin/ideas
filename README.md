# Ideas

## Docker Monitoring

Done this before, but didn't write down the steps for others to replicate. Also, there are some improvements that I want to, like generating daily, weekly, monthly and yearly report on the metrics (CPU usage, memory, SLA etc).

Pair it with Grafana and Prometheus.

## TODO

Trie optimization, and library for the client/server which would allow the data to be more personalized (client-side library) and at the same time up to date with the server's copy (synchronization). Find a way to serialize the data to a more compact format.


## Food for thoughts

- why must the server runs for 24/7? Can't the server just run for a 8hrs a day?
- lifespan of a server, expire after a month
- make the server passwordless. To avoid sending emails, we can just log the email text response with the token to test it out.
- how to handle unexpected error in background task
## TODO: Graphql

- handling table joins (use data loader)
- querying with different data sources (mysql)
- managing multiple graphql (explore federation)
- access controll list
- authorization
- where does business logic reside? Probably used graphql as a read-only data source

## Setting user agent
https://blog.gopheracademy.com/advent-2016/http-client/


## Improved Makefile

Note: use `.PHONY` on non-build targets.

```
objects = foo.o bar.o
all: $(objects)

$(objects): %.o: %.c
  $(CC) -c $(CFLAGS) $<-o $@
```

References:
- https://www.gnu.org/software/make/manual/html_node/Static-Usage.html#Static-Usage
- https://blog.gopheracademy.com/advent-2017/make/
- https://blog.gopheracademy.com/advent-2017/kubernetes-ready-service/


## New Todos

- Infrastructure: Linkerd 2.0, Consul 1.2 Service Mesh, Terraform, Kubernetes Operators
- learn more about message queue use cases and how to implement production-ready message queue
- relook into design patterns for different languages, and microservice architecture and system design.
- go through all the old repositories and update them
- add a github resume and share with others
- put past experiences
- try out the status pattern in database
- design all the schema for social media, travel, hospital and the rest
- ticketing system for manual ops operation
- update the AppSensor implementation
- look at existing job application and try to fill up the gaps (or rewrite them with your expertise)
- look back into data structures and algorithm
- SPTAG (Space Partition Tree And Graph) is a library for large scale vector approximate nearest neighbor search scenerio, which is written in C++ and wrapped by Python
- add timeout session for page when user is idle
- Metrics to measure sequence/funnel
- Group watch with Netflix idea, share the same subscription but pay in group
- Group forms honestbee
- OWASP Top 10, and how to secure your login form.
- Project setup by just using environment variables. The idea is to have a container that initialises all the basic micro service components such as database and message queue, config loading etc. Then we can just set the environment variables to use those infrastructure. The user may choose to extend the container to add new configuration. The idea is similar to go-kit. Rather than providing user options to fill up, we just define the environment variables that the user have to fill in.
- an app to find error in text or grammar, use gamification. But is meant to capture data for machine learning purposes.
- How to create real time streaming architecture
- Update machine learning model in real time
- a platform to ask questions, and find answers
- AID, a platform where you use your knowledge to help others. Earn points, but the sum of the points earned will only be revealed at the end of the week.
- Can I A/B test user with their integer id/hash of the user id modulo. This might not be an accurate indicator, since the even and odd numbered users might not be online. One way is to increment a number for each incoming users and assigning the modulo id to that user to test them.
- Grammar corrector. Enter a sentence you want to validate the correctness. User can submit the corrected version, others can Like or dislike.
- Private eye. Search for something or someone. from just a picture.
- When to use NATs vs Redis Stream vs Kafka. One of the primary reason is the reusability. For example, go nats does not have clients in certain languages, while redis is almost available everywhere.
- Music player for the deaf - through vibration/visualization
- Digital will for the dead - a message that can only be opened in the future
- digital assets - user’s that are popular (reviewer. vlogger, celebrity can have collateral assets, which are their users and also the likes, comments etc). Provide loans to users through with their digital assets as collateral.
- Learn about Facebook Pixel and Google Analytics tracker to capture informative data from the website. Do a sample ecommerce testing and see hwat user clicks the most? Check if the solution can be incorporated with A/B testing and also bandit algorithm.


https://www.datacamp.com/community/tutorials/probability-distributions-python


also, time to update the projects selection and probably host them. Update resume format to display the format too


Look into webassembly for web / or web workers with canvas and see how to speed up large scale web applications online
- also how to fetch data through web workers/service workers and how this will improve the performance
- look into the new webgl specifications

Setting measurable targets
- reduce page load time by 2x
- Reduce steps to upload documents
- Make policies searchable
- Increase memory by making people remember what they did last

once someone has done something, others follow suit. Grab has shown us that they can compete with western giants, so a bunch of startups that will follow the paths will appear suit.
- we have a page menu with categories that allows users to find the categorized products. Can we simplify it and instead show the google-like search page with query understanding that allows users to search for queries like
    - cheapest insurance for flight (displays cheapest insurance for flight comparison and a call to action to buy the product directly)
    - best pwd insurance (displays all pwd insurance products)
    - best pwd insurance life (displays all life pwd insurance product)

Build more websites
- take the data from kaggle such as movie reviews and create actual users and content out of it. Then reverse engine the whole process where they get the user ’s data and how they build the recommendation engine.
- Do the same for flights, email etc


Build a blog that aggregates stories about failures in production and how they mitigate it. The failures can be unexpected, or comes from the initial decision and they hypothesis that went wrong.

Creation of knowledge base, and newsletter weekly to update the changes.

Look into kubernetes recipes, like changing config, hiding secrets.

The opposite of search, recommendation.


## Python data hacks

https://towardsdatascience.com/10-simple-hacks-to-speed-up-your-data-analysis-in-python-ec18c6396e6b

## Scaling

https://medium.com/@evyborov/scaling-up-to-your-first-10-million-users-summary-aws-summit-sf-2017-819dcf532fb7


- How about making a google chrome extension that can execute scripts? Then we can use it to scrape the content and execute the js.

## Analytics

To avoid tracking on testing/development environment, filter the url localhost

https://developers.google.com/analytics/devguides/collection/analyticsjs/
https://segment.com/docs/guides/best-practices/how-do-i-collect-pageviews-on-the-server-side/

# Machine Learning

Statistical data distribution
https://machinelearningmastery.com/statistical-data-distributions/

Probabilitistic distribution
- why are they important?
- how can we use it in our application?

https://bigdata-madesimple.com/how-to-implement-these-5-powerful-probability-distributions-in-python/


## Elasticsearch


How to implement search for web applications?

https://github.com/CatalystCode/CustomSearch
https://github.com/linkedin/instantsearch-tutorial/blob/master/data/stackoverflow/posts_10K.json



URL shortener
http://highscalability.com/blog/2014/7/14/bitly-lessons-learned-building-a-distributed-system-that-han.html


## Vue authentication
https://scotch.io/tutorials/vue-authentication-and-route-handling-using-vue-router

## Sentiment analysis
https://monkeylearn.com/sentiment-analysis/

# Dynamic pricing
https://en.m.wikipedia.org/wiki/Dynamic_pricing
https://www.priceintelligently.com/blog/bid/198355/how-to-implement-a-dynamic-pricing-strategy-without-the-pr-backlash

Architecture and Devops

- Learn traefik, and maesh
- Learn envoy
- Learn istio gateway
- How to implement event sourcing in java
- Useful prometheus metrics? What setup is good
- Terraform scripts for deployment
- How to implement feature toggle correctly. Through env vars
- Domain driven design functional programming
- UML and c4 architecture to solve basic problems like url short energy,
- Solid, code architecture

Art of scalability
- Scalable counting
- Scalable evolutionary architecture through Optimization
- Sampling in scalable software

How to deal with conflicts?
- When someone is not agreeing
- When someone is doing something wrong
- Create an active guideline

https://gist.github.com/manjufy/a91e5813e77eaf632f168ac6576c94da?fbclid=IwAR3a9S66Ecr4QG7ydYyaaZ7JMoUmoWWUrWB5iCd0LVDxU9BToPWqKGcktyw


Functional programming
- How to perform dependency injection with functional programming
- What are strong examples of good usage of functional programming?

Analytics
- Useful statistical algorithms for a/b testing and how to calculate
- How to get the data needed for analytics, what data and how
- How to measure user’s churn

Languages
- Learning java, kotlin, refresher on Haskell

Start be redesigning the different use cases again, how to do multi auth. authentication?
How to design otp?
Designing domain model
- Attributes, scopes, associations
- Behaviours
- Design patterns

Machine learning
- Solving multi tag classification with python

Old recommendation
- for music and songs, sometimes we tend to favour back old songs. why not provide recommendation for old tracks and tastes?

Learning to rank
- How many ways are there to perform ranking
- What is the minimal way to rank (by single attribute, by multiple weighted attributes)




Gotchas
- Always trim string
- Always set character limits


Create portfolio projects

A safer way to set credential? When user open the web, convert local storage to session storage, and put in redux


## Documentation for projects

- Architecture used
- Highlights

Apply ranking based on the user profile
- First determine the user profile categorisation, e.g. break user persona into 16 types. Then determine which bucket the user belongs to
- From the user persona, just pick the personalisation


## Truncate Text logic

Why is this a problem? We don't want a word to be truncated, e.g. apple to be `ap...`, since it will lose it's context. Also, we don't want a sentence to be truncated in front, e.g. `... . This is great` becomes `... . This ...`. It is better to truncate half the sentence of the last sentence when it reaches the threshold for better readability.

Split into sentences, then check char length, then take last sentence and half of it.

## Setting up graphql
- How to perform authorisation
- How to handle caching
- How to separate business logic
- How to handle query joins from mysql? Use data loader
- How to handle n + 1 query
- How to handle support on the client side
- How to handle role
- How to handle graceful termination
- How to handle versioning/backward compatibility
- How to handle integrity (transactions etc?, operations involving associations)

## Grpc best practices
- How to handle grpc calls
- How to setup http calls
- How to perform authorisation, caching and streaming of data
- What advantages does grpc has over graphql or rest http
- What are the standards to design schema
- How to handle versioning/backward compatibility
- Grpc clients
- Grace web/and gateway
- Grace limits (requests and transactions etc)
- Does grpc handle associations well


Dotnetcore

- How to add infra (db, logging)
- How to use Postgres
- How to dockerize
- How to create microservice
- How to test

Golang: react rents will be using the graphql, with a mixture of authorisation server.
- graphql setup
- Authorization/authentication
- Websocket
- Httpserver side push

Scala
- Same as dotnetcore


Message queue learn
- How to use message queue
- Patterns in message queue
- Durability/resiliency
- Autoscaling of message queue
- Types of client library
- Retry pattern
- Asynchronous communication with message queue, and how it differs from synchronous
- Applications/use cases with message queue
- Saga pattern with message queue
- Can message queue be used to prevent duplicate requests?


Algorithm
- Write an algorithm to get the largest gain from stocks buying and selling

Service worker


- How does it work?
- How to cache api requests/ json response offline?
- How to implement background fetch
- How to optimise the server side events



https://pwa-workshop.js.org/4-api-cache/#cache-update-refresh


Offline Google Analytics events

https://medium.com/@addyosmani/progressive-web-apps-with-react-js-part-3-offline-support-and-network-resilience-c84db889162c

Implement shadow banning
- How does shadow banning works?
- Twitter does not implement shadow banning https://blog.twitter.com/en_us/topics/company/2018/Setting-the-record-straight-on-shadow-banning.html

# Reducing repetition

Code generator

## Games to buil
basic pokemon
werewolf

## Voice application

Real-time censoring of vulgarity

Coding with voice
- [Serenade](https://serenade.ai/)
- [Talon](https://talonvoice.com/)


- implement event Sourcing/CQRS architecture
  - https://paramore.readthedocs.io/en/latest/BrighterOutboxSupport.html
  - https://www.cosmicpython.com/book/preface.html
  - https://microservices.io/patterns/data/event-sourcing.html
  - https://buildplease.com/pages/fpc-10/
  - https://cqrs.nu/Faq/command-handlers
  - https://softwareengineering.stackexchange.com/questions/386710/confused-about-commands-domain-events-and-external-events-in-event-sourcing
  - https://www.rahulpnath.com/blog/avoid-commands-calling-commands/
  - command vs event handlers https://groups.google.com/g/axonframework/c/7pURn8XboSc
  - https://www.petermorlion.com/849-2/
- learn how to maximize rule engine: https://docs.drools.org/6.0.0.CR3/drools-expert-docs/html_single/#d0e448
- learn saga orchestration https://www.infoq.com/articles/saga-orchestration-outbox/
- learn to create slack bot integration for work approval https://slack.com/intl/en-sg/slack-tips
- learn Nix and NixOS
  - https://tech.channable.com/posts/2021-04-09-nix-is-the-ultimate-devops-toolkit.html
  - https://nixos.org/guides/nix-pills/why-you-should-give-it-a-try.html
- learn to create a CRM https://www.zendesk.com/blog/what-is-a-crm-database/
- how to use google protobuff to version your entities (could be used as the usecase layer)
- architecture for one-man startup https://anthonynsimon.com/blog/one-man-saas-architecture/
  - how would you design it? what's the most cost effective deployment strategy (finops)
- revise pandas, rust again
- learn temporal patterns
  - how to create immutable data structure with postgres
  - how to ensure continuous time range
- parameterizing jupyter notebooks, and how to save/load readme
- summarize thoughts on mocking database during testing, and other best practices
  - https://qvault.io/clean-code/writing-good-unit-tests-dont-mock-database-connections/
- how to implement your own state machine (for saga also), based on AWS Sage Maker
  - https://step-functions-workshop.go-aws.com/30_setting_up_our_services/10_preparing.html
- microservice timeout, jitters https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf?did=ba_card-body&trk=ba_card-body
- solving distributed transaction problem with saga
  - https://developer.ibm.com/depmodels/microservices/articles/use-saga-to-solve-distributed-transaction-management-problems-in-a-microservices-architecture/
  - https://temporal.io/usecases#transactions
  - https://www.infoq.com/articles/saga-orchestration-outbox/
- message broker vs db queue
  - https://stackoverflow.com/questions/48099098/message-broker-vs-database-and-monitoring
  - https://softwareengineering.stackexchange.com/questions/351449/message-queue-database-vs-dedicated-mq
  - https://www.cloudamqp.com/blog/why-is-a-database-not-the-right-tool-for-a-queue-based-system.html
  - https://medium.com/galvanize/message-queues-in-database-transactions-f830718f4f12
  - https://medium.com/galvanize/message-queues-in-database-transactions-f830718f4f12
- learn to implement authorization with OSO
- why is authorization not part of domain in DDD?
- Python Jupiter interactive

https://queirozf.com/entries/interactive-controls-for-jupyter-notebooks-python-examples#-ipkernelapp-warning-widget-javascript-not-detected-it-may-not-be-installed-or-enabled-properly

Jupiter tips

https://www.dataquest.io/blog/jupyter-notebook-tips-tricks-shortcuts/

https://towardsdatascience.com/optimizing-jupyter-notebook-tips-tricks-and-nbextensions-26d75d502663?gi=25a7e9f0de9e

Immudb for event sourcing?

https://www.codenotary.com/technologies/immudb/

CQRS bulk update

https://enterprisecraftsmanship.com/posts/ddd-bulk-operations/

https://softwareengineering.stackexchange.com/questions/420689/bulk-update-of-ddd-aggregate-roots

https://blog.sapiensworks.com/post/2013/12/16/Bulk-Actions-With-DDD-And-CQRS.aspx

https://github.com/rogchap/v8go

https://softwareengineering.stackexchange.com/questions/420689/bulk-update-of-ddd-aggregate-roots

Where to ddd autoriaxtin

https://stackoverflow.com/questions/50456199/ddd-implementing-authorization-invariants

https://stackoverflow.com/questions/21730464/which-layer-should-be-used-for-user-authentication

https://lessthan12ms.com/authorization-and-authentication-in-clean-architecture.html

http://domain-driven-design.3010926.n2.nabble.com/why-is-authorization-in-a-separate-layer-from-the-model-td7578909.html

https://softwareengineering.stackexchange.com/questions/367659/implementing-ddd-users-and-permissions

https://vaadin.com/learn/tutorials/ddd/ddd_and_hexagonal

https://medium.com/@martinezdelariva/authentication-and-authorization-in-ddd-671f7a5596ac

https://stackoverflow.com/questions/38002961/implementing-user-defined-business-rules-with-ddd

https://builtwithdot.net/blog/where-do-i-put-my-business-rules-and-validation

Security in ddd

https://www.utwente.nl/en/eemcs/trese/graduation_projects/2008/Uithol.pdf#page54

Cel-go basics

https://mycodesmells.com/post/introduction-to-cel-go

Sql for data analysis

https://hakibenita.com/sql-for-data-analysis

aI in manufacturing

https://haker88.medium.com/hands-on-tutorial-for-ai-implementation-in-manufacturing-part-1-55adff94d1e6

AWS lambda function

https://medium.com/creditorwatch/aws-lambda-facts-you-wish-to-know-before-processing-2-billion-lambda-executions-2021-78fe77183c80

Typescript project 2021

https://www.metachris.com/2021/04/starting-a-typescript-project-in-2021/

Rules engine

https://news.ycombinator.com/item?id=19957377

Html5 sanitizer

https://wicg.github.io/sanitizer-api/

Lazy loading javascript data

https://humanwhocodes.com/blog/2021/04/lazy-loading-property-pattern-javascript/


Typescript permissions

https://spin.atomicobject.com/2021/04/26/modeling-permissions-types-typescript/

Filter dsl elasticsearch

https://www.elastic.co/guide/en/elasticsearch/reference/current/sql-rest-filtering.html

Clean react projects

https://betterprogramming.pub/21-best-practices-for-a-clean-react-project-df788a682fb

Postman integration testing with Newman

https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/

https://medium.com/velotio-perspectives/api-testing-using-postman-and-newman-6c68c33303fc

How to rollback data?


Sandboxed embedded languages

https://www.innoq.com/en/blog/go-plugins-with-javascript/

https://pwnisher.gitlab.io/nodejs/sandbox/2019/02/21/sandboxing-nodejs-is-hard.html

https://github.com/patriksimek/vm2

https://www.freecodecamp.org/news/running-untrusted-javascript-as-a-saas-is-hard-this-is-how-i-tamed-the-demons-973870f76e1c/

https://forum.golangbridge.org/t/help-creating-go-sandbox-to-execute-untrusted-golang-code/20941

https://www.lambrospetrou.com/articles/golang-v8-isolates/

https://github.com/rogchap/v8go/blob/master/function_test.go

https://stackoverflow.com/questions/10937870/how-to-run-untrusted-code-serverside

https://github.com/laverdet/isolated-vm#who-is-using-isolated-vm

https://hmarr.com/2013/oct/16/codecube-runnable-gists/

https://www.npmjs.com/package/vm2

https://github.com/asvd/jailed

https://github.com/postmanlabs/postman-sandbox/blob/develop/lib/sandbox/console.js

https://github.com/rogchap/v8go

Anomaly detection

https://github.com/adobe/OSAS

Contribute to open source

https://opensource.guide/how-to-contribute/

Rust grpc

https://dev.to/rkudryashov/introduction-to-grpc-in-rust-4dgg

Immutable Postgres

https://dzone.com/articles/how-to-mutate-data-in-a-system-designed-for-immuta

https://enter-haken.github.io/posts/2017-07-15-database-architecture-part2.html

https://blog.sentry.io/2019/10/25/how-to-mutate-data-in-a-system-designed-for-immutable-data

https://kevinmahoney.co.uk/articles/immutable-data/

https://gist.github.com/ghl3/7e8147ae4dcf08f3d325

Crdt

https://debezium.io/blog/2019/02/19/reliable-microservices-data-exchange-with-the-outbox-pattern/

https://www.serverless.com/blog/crdt-explained-supercharge-serverless-at-edge

https://www.baeldung.com/java-conflict-free-replicated-data-types

https://news.ycombinator.com/item?id=7735141

https://www.infoworld.com/article/3305321/when-to-use-a-crdt-based-database.html

https://naveennegi.medium.com/rendezvous-with-riak-crdts-part-1-e94cfc8fe091

https://stackoverflow.com/questions/63597403/choreography-sagas-in-ddd-chain-of-integration-events

https://cloudstate.io/old/docs/core/current/user/lang/java/crdt.html

https://ntnuopen.ntnu.no/ntnu-xmlui/bitstream/handle/11250/2656668/no.ntnu:inspera:48729278:32233568.pdf?sequence=1

https://kalele.io/summary-of-crdts/


Creating a job queue

https://www.holistics.io/blog/how-we-built-a-multi-tenant-job-queue-system-with-postgresql-ruby/

https://www.2ndquadrant.com/en/blog/what-is-select-skip-locked-for-in-postgresql-9-5/

http://johtopg.blogspot.com/2015/01/queues-queues-they-all-fall-down.html?m=1

https://cargopantsprogramming.com/post/queues-in-postgres/

https://camunda.com/blog/2020/02/the-microservices-workflow-automation-cheat-sheet-the-role-of-the-workflow-engine/

https://docs.temporal.io/blog/workflow-engine-principles/

Postgres hashtext and limit category

https://www.depesz.com/2021/01/08/how-to-limit-rows-to-at-most-n-per-category-fix/

Git check conflict without merging them

https://stackoverflow.com/questions/10879331/how-to-check-the-conflict-of-two-branch-but-not-need-to-merge-them

https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History

https://about.gitlab.com/blog/2018/06/07/keeping-git-commit-history-clean/#situation-3-i-need-to-add-remove-or-combine-commits

Useful go Lib

https://github.com/uber-go/gopatch/blob/main/docs/PatchesInDepth.md#statements
Gocmp
Golang I lint
Go mock
Golang desktop app https://wails.app/tutorials/quotes/

https://developer.fyne.io/architecture/scaling



Working with csv 

https://openrefine.org/download.html

https://www.w3.org/TR/tabular-data-primer/

https://blog.openbridge.com/how-to-do-csv-file-validation-and-schema-generation-43a9cb78e1eb

https://datatracker.ietf.org/doc/html/rfc4180

https://digital-preservation.github.io/csv-schema/#toc4


Ideas
Upload data to infer schema
Validate schema
Set required fields

Extras
Role Actor: system, guest, user, admin, infra: db
Action: read
Resource: user


Message: failed to find user
Code: user.not_found use constant int with stringer but don’t expose int, just string. With start and end
Kind: not found, already exists, permission denied, failed precondition, internal

https://github.com/grpc/grpc-go/blob/v1.12.0/codes/codes.go

https://middlemost.com/failure-is-your-domain/

Extra: map

Type Error

Func userError(kind, code. Builder pattern
Loss of information
Not enough data
Domainerrors should be error sentinel, errors at outer layer should warp domain error

Polymorphic solution
Use multiple columns, but have one universal id and type column that is indexed. The id is ideally unique

Where should go interface live?

https://groups.google.com/g/golang-nuts/c/WlvWfPjGncY


Auth security

https://supertokens.io/blog/the-best-way-to-securely-manage-user-sessions

https://datatracker.ietf.org/doc/html/rfc6819

https://evertpot.com/jwt-is-a-bad-default/

https://supertokens.io/blog/are-you-using-jwts-for-user-sessions-in-the-correct-way


Username

https://stackoverflow.com/questions/12018245/regular-expression-to-validate-username

https://stackoverflow.com/questions/62882865/postgres-generate-a-unique-username

Hash password token

https://stackoverflow.com/questions/20013672/best-practice-on-generating-reset-password-tokens


Api design with me

https://stackoverflow.com/questions/36520372/designing-uri-for-current-logged-in-user-in-rest-applications

https://stackoverflow.com/questions/35719797/is-using-magic-me-self-resource-identifiers-going-against-rest-principles

Jupiter must have extensions

https://towardsdatascience.com/5-extensions-that-will-make-you-switch-to-jupyter-lab-32c6b66ac755#c97e

Ideas

https://samsquire.github.io/ideas/

Geocoding mapbox

https://www.smashingmagazine.com/2021/06/building-geocoding-app-vue-mapbox/

Go implements interface

https://stackoverflow.com/questions/10498547/ensure-a-type-implements-an-interface-at-compile-time-in-go/34619122#34619122


DevOps 
Stop Rds

https://aws.amazon.com/blogs/database/schedule-amazon-rds-stop-and-start-using-aws-lambda/

Does fb use joins

https://www.quora.com/Does-Facebook-use-join-operation-on-database-tables-to-load-whole-profile-of-user-if-yes-How-many-join-operation-Facebook-do-to-load-the-profile-how-many-databases-tables-they-have-1-Billion-data-of-objects-is-really-big-deal

Vim advance

https://thevaluable.dev/vim-veteran/

Build webhook

https://keygen.sh/blog/how-to-build-a-webhook-system-in-rails-using-sidekiq/


Automerge and conflict resolution

https://docs.aws.amazon.com/appsync/latest/devguide/conflict-detection-and-sync.html https://docs.aws.amazon.com/appsync/latest/devguide/conflict-detection-and-sync.html

https://github.com/yjs/yjs

https://github.com/automerge/automerge

https://hasura.io/blog/couchdb-style-conflict-resolution-rxdb-hasura/


Event sourcing handle duplicates

https://groups.google.com/g/dddcqrs/c/h17Tjxtz5w4

https://stackoverflow.com/questions/31386244/cqrs-event-sourcing-check-username-is-unique-or-not-from-eventstore-while-sendin


Db critic

https://www.channable.com/tech/dbcritic-constructively-criticizing-your-postgres-schema

https://ardentperf.com/2021/07/06/paranoid-sql-execution-on-postgresql/

Aws

https://medium.com/edataconsulting/how-to-get-a-ssl-certificate-running-in-aws-elastic-beanstalk-using-certbot-6daa9baa3997

Big data

https://dvc.org/doc/start

https://docs.delta.io/latest/quick-start.html


Golang code generation

- ideally for decorators, removing this does not impact usability

https://mattermost.com/blog/opentracing-for-go-projects/
