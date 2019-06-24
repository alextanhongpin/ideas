# Ideas

## Webhook Server

Design an architecture for a webhook server and integrate it successfully.

## Storing data in IPFS

Look into how to create DAP (decentralized application). 

## Compare IPFS, Swarm etc.

Also look into Whisper. Try to implement a simple project with it.

## Genetic Algorithm

Write your own implementation of Genetic Algorithm and look into the application in web/mobile. Compare it against stochastic gradient descent. Also, understand that Genetic Programming and genetic algorithm is different.

## Neural network

Write your own neural network and look into the basic applications. Implement in different languages (go, node, python, rust, haskell).

## Developer Page

Scrape github user's data from malaysia and perform a job search/developer search based on personality and specialization. Write your own recommendation engine and get feedback from users whether it's relevant or not, and perform learning from there.

## Clones

Finanz Revamp, Residenz, Instagram clone, Facebook, what is X is Y (what if JobStreet is Facebook?). Point-of-Sale system for food ordering, lorry tracking system. A clone of Journal.


## Imbalanced Dataset Machine Learning

Reference [here](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwi2_ISImcXXAhUBLY8KHaS9BkAQFggxMAE&url=https%3A%2F%2Fwww.analyticsvidhya.com%2Fblog%2F2017%2F03%2Fimbalanced-classification-problem%2F&usg=AOvVaw18t2VQ8g39iZnlFc8a7O4t) and [here](https://machinelearningmastery.com/tactics-to-combat-imbalanced-classes-in-your-machine-learning-dataset/).

## Sudoku Solver

Look into how to solve sudoku uisng the `Dancing Links` and `Algorithm X` algorithms. Working solution with TypeScript [here](https://github.com/alextanhongpin/algorithm-x).

## Singleflight pattern

Look into the singleflight pattern for subscribing to connection. http://www.cs.duke.edu/courses/cps296.4/fall13/838-CloudPapers/dean_longtail.pdf. Also look into connection pooling in Golang, and sync.Once.

## Future of Web Apps

How would the future of web apps look like? Design conceptual websites with modern technologies.

## LambdaMART

Part of learning to rank

Understand the LambdaMART algorithm and use it to create ranking system.

## Technical Indicators

Try out all the possible technical indicators and write the algorithm in Python Jupyter. Also, run it against a real test data, plot it out and visualize the outcome. See if they can be used for prediction. Also, check if you can do image pattern matching against the popular technical indicators. Repo [here](https://github.com/alextanhongpin/technical-indicators)

## Decentralized Applications

Check out how to create and deploy a simple dapp. Also, check out solutions for distributed databases. 


## Minimal Docker images

For rust, haskell, golang, node, scala and python. Write down the size and multi-stage build process.


## Machine Learning Softwares

Check out the PredictionIO, Apache Mahout and Elastic Search More Like This performance.

## Stable Marriage Problem

Look into how to solve stable marriage problems and test it on timetable allocation, dorm room allocation to students, candidates and hirers application and ...finding best dating partner. Wiki link [here](https://en.wikipedia.org/wiki/Stable_marriage_problem).

Solution in several languages can be found [here](https://github.com/alextanhongpin/stable-marriage-problem).


## Basic and advanced algorithms

Bubble sort, quick sort, shellsort, merge sort, etc. Learn the different kinds of sorting and then look into dynamic programming. Knapsack problem, and coin changing problem.

## Docker Monitoring

Done this before, but didn't write down the steps for others to replicate. Also, there are some improvements that I want to, like generating daily, weekly, monthly and yearly report on the metrics (CPU usage, memory, SLA etc).

Pair it with Grafana and Prometheus.

## Sperner’s Lemma

Algorithm for splitting rent.

## Evolutionary Architecture

I wanted to design an architecture called Perfect Architecture before - only to realize there is no such thing as perfect. It is always `it depends`-architecture and should be designed based on the use cases. But evolutionary architecture is something that I would like to advocate - it mimics the human process and has a brain (machine learning/deep learning) and has a pipeline (whatever organs in the human body has), has self-healing and functions as a whole.

## Token Bucket & Leaky Bucket

Look into how to implement those algorithms in different languages.

## SASS

"Servicify" everything that you have done, with Kubernetes/Nomad as the scheduler. Include proper unit tests for each services too, and best practices.


## Keras Text Processing

Look into the different areas of text processing and understand how to apply keras to it. Also look into Spacy for chatbots and learn how to dockerize them.


## Yik Yak

Make an app like Yik Yak, that will messages that will expire after certain days. Also, add sentiment analysis to create postive text rather than negative.


## Evolutionary Microservices Architecture

While working on a notification delivery system, we came up with different versions of the services. The services are broken up into several microservices, and most of the time we need to work on optimizing them (rewrite in other languages etc.). But a lot of time is wasted carrying out performance testing to identify which version is better (higher request rate, lower latency etc.). The idea is to take the concepts of genetic programming to discover the strongest candidate.


## gRPC Healthcheck

## WebSub

Look into websub and how to implement it.

## Istio/Conduit/Linkerd/Nomad

Learn the basics of Istio and Conduit and create examples. Also look back into Nomad and Linkerd.




## Elasticsearch Syncing with MySQL and MySQL Migration

Utilise CDC (change data capture) to sync data from MySQL/Postgres to Elasticsearch. Check to ensure how they handle schema changes (removal/addition of new columns) and creation of new tables as well as deletion.

If there are constraints, set the rule to allow only addition, not removal of columns. Deprecate it and warn end users about it. If there are fields that are rapidly changing but does not require indexing, store the data as a json object in a new column. Else, just use nosql.

To prevent users from performing addition/deletion, create a new user and limit the access.




## Cloud Native apps with microservices architecture

- Building and Deploying a Microservice 
- Discovery and Invocation 
- Microservices Patterns 
- Circuit Breakers 
- Pipelines 
- Authentication 
- Logging, Monitoring, and Tracing 
- Blue-Green Deployment 
- Canary 
- Moving from Monolith to Microservices 

## Latency Issue Debugging

check cpu, memory usage, allocations, goroutines stack trace

Request tracing tools
- nettrace, openzipkin, `opencensus`



## Etherscan Viewer

Create a viewer like etherscan that caches the data in redis to speed up read. It will also

- display transactions/blocks
- search function
- filter function
- sort function


## Signal

See how to implement encryption in applications:
https://github.com/signalapp/libsignal-protocol-javascript


## Better documentation for repository

Some thoughts on the do's and dont's.

The dont's:
- the installation for the language. If the repo is meant for golang, it already assumes that the user has golang installed on the development machine


For the dos', let's take some inspiration from the [twelve-factor-app](https://12factor.net/):
- codebase: N/A
- dependencies: include dependency (package management version/commands etc, how to install/rebuild)
- config: the environment variables required, and where to find/generate them. Should provide a good default too
- backing services: external resources/links such as database, cloud platforms, where to find them/setup/cli tools etc
- build, release, run: proper steps/pipeline to rebuild the application and deploying/running them. Also how to test them in different environment/to know if it's working as expected (through test cases)
- processes: how to run the application/external dependencies as isolated process (use docker)
- port binding: N/A
- concurrency: N/A
- disposability: how to start/stop/cleanup application state, also how to terminate the instance. try to design a lifecycle for it.
- dev/prod parity: again, docker
- logs: logging best practices/naming/tracing through resource id etc
- run admin/management tasks as one-off processes: database migration tools, terminal commands, scripts, makefile etc.

And some others:
- application versioning


## ChatOps

Deploy with Slack commands, for `dev` and `stage` anyone can deploy, for `prod` need consensus from at least 2 person:

```
\deploy app-name staging
```



## Slicing a monolith


## CRDT, Bloom Filter

Read and find out about [RaiBlock](https://raiblocks.net/), [IOTA](https://www.iota.org/), Directed acyclic graph (DAG), Distributed Hash Table (DHT), Merkle tree, cross chain bridges, bloom filters, cuckoo hashing, conflict-free replicated data ([CRDT](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type)), Nash Equilibrium, Puppeth...

Look into distributed hash table http://ntrg.cs.tcd.ie/undergrad/4ba2.05/group6/index.html, and CHORD implementation https://en.wikipedia.org/wiki/Chord_(peer-to-peer)

## Actively Pursuing

- Site Reliability Engineering
- Languages: Haskell, Rust, Scala, Nim, Python 3.7, NodeJS, Elixir
- Infrastructure: Linkerd 2.0, Consul 1.2 Service Mesh, Terraform, Kubernetes Operators
- Blockchain: White papers
- Data structures and algorithm: https://en.wikipedia.org/wiki/Ford%E2%80%93Fulkerson_algorithm

## Leslie Lamport

Look into his past work, including the Byzantine General Problem, and [The Part-Time Parliament]( https://lamport.azurewebsites.net/pubs/lamport-paxos.pdf)

## LXC, LXD and HyperContainer

Only works on linux for now.
https://docs.hypercontainer.io/index.html


Also other alternatives like kata container, virtlet etc

## How to perform traffic multliplexer

Rather than performing blue-green in production, would it be better to multiplex the traffic to both production and staging environment. This reduces the effort to manually test the staging environment. Also, is it possible to rollback the state (time-travel) if there are errors in order to have a clean state. Of course, the danger of duplicating the data is also security related. 


## Kiali

https://github.com/kiali/kiali

Observations using kiali and opentracing, it doesn't have to be real-time. They are basically gathering metrics through different means (e.g., prometheus). It is always good to be able to time-travel back at the time some incident happen. Also, https://opencensus.io/introduction/


## How does uber payment works?

User book a cab, but the payment is done after the user arrive at the destination. What happens if the user disconnect (intentionally or not) halfway during the trip?

Implementing dynamic pricing is also possible. 

## Evolutionary Algorithms 

Look into ant colony optimization, particle swarm optimization etc and see how to apply it to actual problems (TSP, etc). Also look into generating the solutions in a different way (iterators, generators) and create canvas html simulations.
http://www.cleveralgorithms.com/nature-inspired/index.html

## Ultimate Tic Tac Toe

Create solution for this (monte-carlo tree search)

## Collaborative Filtering

Using One Slope algorithm for binary ranking (1, 0)

## Solving Docker Image issue

Sometimes the new application that we are deploying is not working (especially in AWS, when adding new environment variables), and it will keep crashing in an infinite loop. Solution is to deploy a dummy nginx instead of our complex application, cause it will just display the dummy 504 page. A better alternative is to create a custom server that display a dummy 500 page.


## IDM (Internet Downloader Manager)

Create a basic version of internet downloader manager.

## Look into distributed synchronization protocols and implement a basic working example

## Look into operational transformation

## Look into grapheme cluster
Something to do with the unicode encoding.
http://unicode.org/reports/tr29/


## Compression
Check out algorithm for compressed inputs, such as LZ77 (grammar-based compression) and Boldi-Vigna (graph compression).

## Dendogram
Hierarchical clustering and how to generate such clusters.

## Algorithms

This is taking too much time, results are there, but probably focus more on the application rather than performance. Also, write a few articles to describe how it can be applied in real-world scenarios. Also, find way to turn the algorithms into applications. Probably would be interesting if things can be visualized.


## Meta Tags

In html, you can get more information from users through click analysis. But just clicking the region would not give much indication on what the user like. So, it's probably interesting to inject metadata to each elements, metadata that contains much more information that is obtained either manually or through machine learning.


## W3C Web Authentication

https://www.w3.org/TR/webauthn/

## OpenCV to detect Sudoku Board

And complete the sudoku puzzle with dancing links


## Apply Modular Crypt format for Argon2

https://passlib.readthedocs.io/en/stable/modular_crypt_format.html deprecated in favor of 
https://github.com/P-H-C/phc-string-format/blob/master/phc-sf-spec.md

## Learn about fuzzy testing

https://en.wikipedia.org/wiki/American_fuzzy_lop_(fuzzer)

In golang, the `quickcheck` package can be used to do testing too.

## Using client processing power

Find ways to make client do more work and send statistics to the server rather than performing the job on the server side. This delegation allows the work to scale across and the server is only responsible for validating and storing the data they received from the client.

Check the implementation of [hashcash](https://en.wikipedia.org/wiki/Hashcash) and see how to implement a basic one.

## Fire Alarm

Inspired by OWASP AppSensor. Implement something like a fire alarm trigger to disable certain parts of the application when there are possible attackers. I've been wondering how to make full use of logs, (context logs with correlation id, open tracing, open census), just storing them is not enough. There need to be some action that needs to be done. Also, when an application is experiencing high traffic, it should not affect the whole instance - only the pipeline that is affected should be regulated. 

Do a pipeline-style architecture that can be dropped when attacked. Create a log analysis mechanism too.

## p2p 

design a p2p network for synchorization of data. It requires the capabilities to detect new peers/drop existing peers, and searching for the best peer to sync data. Also, malicious peers should be dropped.

- p2p distribution of data is a little complicated. There's no way to ensure equal distribution of data among the nodes. Consider the following - what happens when there are no nodes? There are no source of data. What happens when we set a restriction so that only one node can process x amount of data. It might work for reasonable size of node, but when there is only one node left, it will get locked from sending the data. If there are too many, the peers will be busy looking for other nodes to check if they can provide the data. 
- also, the data transferred/synced between peers must be immutable. Consider the case where the data is constantly changing - then the peer have to resync it all the time. It can still work if the data is small, private and personal to a user (think Dropbox), but for data that is shared publicly, it should be immutable.
- nodes are divided into probably a few categories - those that are static/trusted or those that are publicly run by users. Users can run peer nodes in order to reduce the load of the server. But there has to be some rewards associated with the work they have done (incentives) in order to encourage them to continuosly host them. Also, where is the single source of the data (golden record), because if the peers delete the data then the data can only be served through the static host - which also means that the static host can serve anything. Are there any way to distribute data permanently in the web?


## TOCTOU
Time to check, time to use race condition. Read on it and how to prevent it.

## Designing a proper security pipeline.
## Test entropy of random numbers with NIST statistical test suite
## How does the redis TTL works

https://redis.io/commands/expire
Implement one version in golang, which takes advantage of the hash map random order to expire the first 20% of the keys.

## How to block ip address?
https://husobee.github.io/golang/ip-address/2015/12/17/remote-ip-go.html


## Consistent Hashing
Learn and implement consistent hashing. Also check out their use cases and how to apply them.


## Questions
- how to handle anonymous session/best practices and why do we need to do it (prevent attacks, fingerprint user)
- is sessionid using uuid secure? also look at the mysql uuid to binary to see how we can save bytes
- how to block ip address, and better way to fingerprint user
- how does redis ttl works (solved, can create a naive implementation using golang)
- NIST statistical test suite to test random number
- how to secure ajax
- TOCTOU (time of check, time of use race condition)
- how to design a proper security pipeline in CI/CD (git pre-commit check, zed attack proxy docker)
- handling caching for client side. One way is to return a version for each api response. When calling the first api call, check the version and see if the data needs to be prefetched.
- reducing string storage size with 16bits http://www.kinematicsoup.com/news/2016/9/6/data-compression-bit-packing-101



## Identifying values in services

We may deploy hundred services, but how do we define the values of those services? Often, we question ourselves on how to write microservices, what are the boundaries of the services, why should it be designed that way, but we overlook the most important question - what is the value of a service?

How do we measure the value of the service? The most naive one is through the usage. Consider the following:

```
Services    Calls/day      Availability
Service A   100000         99%
Service B   1000           98%
Service C   10             100%
```

Here we see that service C has the least call. If a service does not deliver value, it is wise to remove it.
For services that consumes a lot of call, we can probably segregate the data by users to see who calls it more often - this can lead to more interesting discovery like why the user calls the service often, and what can be done to improve the service (custom-tailor microservices).


## AES-GCM vs AES-CBC for encryption

https://security.stackexchange.com/questions/184305/why-would-i-ever-use-aes-256-cbc-if-aes-256-gcm-is-more-secure

## Reactive System

Most of the time, we build applications hoping for users to interact with them. But what if we can bring the interaction out of the application? Take for example:

- push notification to notify when you are around somewhere (beacon/geolocation)
- notification to notify when a weather is about to change/earthquake detection
- an app senses that you are in danger and make a call/message others
- detect that a train is reaching soon 
- notify when you are close to a destination

## MutationObservers, WeakMap, WeakSet JS, CustomElements

Also sharedWorker with websocket. https://blog.pusher.com/reduce-websocket-connections-with-shared-workers/

Build your own approach to designing components without framework.

## NewsFeed 3D
Build 3D overlapping news feed where new news will just pop on top of older ones. When selected, it will change into the standard list views.

## TODO

Trie optimization, and library for the client/server which would allow the data to be more personalized (client-side library) and at the same time up to date with the server's copy (synchronization). Find a way to serialize the data to a more compact format.

## How to ensure that anonymous user does not break certain flows (purchase, registration etc)? 

Create a single unique session that will expire (or can only be used once) and send them a link with that token through email. For each steps, assign a unique bits (1, 2, 4, 8 etc). The email link can only be visited once. If the user complete a step, mark it. If they try to break the steps, forbid them, or ask if they want to restart the flow. The flow can only go in one direction, restarting means repeating the steps from the first one. How to avoid spam (user sending it to another email?). By adding more constraints like the sending can only be done every 5 minutes etc.


## Food for thoughts

- why must the server runs for 24/7? Can't the server just run for a 8hrs a day?
- lifespan of a server, expire after a month
- make the server passwordless

## AOP
Aspect-oriented programming, and how it could be use to modularize functionalities. Stuff like decorators for throttling etc.

## Learn how to algorithmize decisions

- decision trees etc.

## Stuff to learn

- OpenTracing nginx integration
- learn crystal/rust programming language basic and work on a simple project
- linkerd 1.6 and 2.0 updates 
- find out how to do consistent hashing in different languages (golang, nodejs, python etc)
- learn more about message queue use cases and how to implement production-ready message queue
- relook into design patterns for different languages, and microservice architecture and system design.

## Write use cases
- take a look at old projects (chat, websocket, social media etc) and write some use cases
- write use cases for passwordless project
- also take time to write an implementatio for server sent events and websockets with the background task worker with different languages
- look into how to integrate background notification for websocket events

## Write the three principles

## TODO: Graphql

- handling table joins
- querying with different data sources (mysql)
- access controll list
- authorization
- where does business logic reside? Probably used graphql as a read-only data source

## Api Designs

- throttling, backoff, circuit breaker and rate limit
- rate limit by ip (throttle individual requests)
- rate limit by ip + path (throttle individual usage for specific endpoint)
- circuit breaker for error? when a user type in wrong password three times
- request id library (make it modular)
- caching json response?
- ttl map for golang (similar like redis EXP)

## Golang struct order
https://medium.com/@felipedutratine/how-to-organize-the-go-struct-in-order-to-save-memory-c78afcf59ec2

## How redis expires keys
https://redis.io/commands/expire

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

TODO:

- go through all the old repositories and update them
- add a github resume and share with others
- put past experiences
- try out the status pattern in database
- design all the schema for social media, travel, hospital and the rest
- implement SRE practices
- ticketing system for manual ops operation
- update the AppSensor implementation
- look at existing job application and try to fill up the gaps (or rewrite them with your expertise)
- look back into data structures and algorithm
- SPTAG (Space Partition Tree And Graph) is a library for large scale vector approximate nearest neighbor search scenerio, which is written in C++ and wrapped by Python
- Document classification
- learn and implement back the software design patterns
- https://en.wikipedia.org/wiki/Software_design_pattern
- https://medium.com/@marinithiago/doing-event-sourcing-without-building-a-spaceship-6dc3e7eac00

- Learn and implement nimlang, crystal, scala, python and kotlin again
- add timeout session for page when user is idle
- Metrics to measure sequence
- Measure the number of calls for endpoint by user. If a lot of requests is made by a user for login, they might be hacking
- Stateful rest Api design with state machine
- Machine learning anomaly detection refresher
- rate limiting and throttle, they are two different things. Both are enforcing a policy. But we often talk about application level rate limiting (max 10000 requests per second) and consumer rate limiting (5 req per second), but they are actually not the same. The former is daily throttle quota, the latter is rate limit usage.
- Learn nats/redis/kafka
- Learn Postgres
- Learn Kubernetes, Consul, Nomad, Terraform, Prometheus
- Group watch with Netflix idea, share the same subscription but pay in group
- Group forms honestbee
- OWASP Top 10, and how to secure your login form.
- Project setup by just using environment variables. The idea is to have a container that initialises all the basic micro service components such as database and message queue, config loading etc. Then we can just set the environment variables to use those infrastructure. The user may choose to extend the container to add new configuration. The idea is similar to go-kit. Rather than providing user options to fill up, we just define the environment variables that the user have to fill in.

Active service pattern is just a cron job. How to pull data periodically? Return the last update date. MD5 hash the content, or check if the updated date is greater than the previously updated data. If you are pulling a collection, then the greatest last updated date is the indicator.

Useful patterns for data
- Tag the start date. This allows us to know if the report is indeed stale or not. Always strive to produce a better ones.
- add similar tags

Parse pdf
- Read the text from the pdf and summarise it. Allow users to ask questions about the summarised text. 
- Categorize the pdf according to the type. Perform supervised and unsupervised learning

Create user profile for each individuals.
- Store the actions/events/behaviours in a bucket for each user
- Whenever a new user action is performed, gather the metrics
- For each metrics, assign a behaviour, e.g. if the user login actively, give them the behaviour “active user”

Upload documents/data
- allow users to ask questions on the documents they uploaded. For example if it is an insurance policy, users can ask if they are covered for certain incident

https://instagram-engineering.com/storing-hundreds-of-millions-of-simple-key-value-pairs-in-redis-1091ae80f74c

- Business rules requires facts to be gathered first. Facts are deduced by events. We can have facts on

- Something that is supposed to happen once, e.g. user selects an order
- Something that is supposed to happen twice. User calls the service twice
- Something that is supposed to happen multiple times.
We can take the statement above and apply the NOT logic. 
We can also compose multiple of those occurrences with AND, OR , WHEN, ALL, SOME etc.
We can set a TIME WINDOW, turning them into time series events.
- sequence of events is even harder. There are predecence, or concurrent. The former states that an action must occur before the next, the latter states that both can happen at the same time)

A simple rule to check the user’s home address can be based on the following facts:
- Fact 1: Location of user when the time is 2-3 am
- Fact 2: The highest frequency of the location for 1 week.
- The business logic will then be to sort the locations with the highest frequency and return them
- That concludes the rule check user home address

We can extend that to:
- Check users change address. If the same pattern is repeated above and the value differs from the previous location, then trigger the user change address rule.
- Check user’s work address. We just need to change the time to check to 10-12 am. (before lunch). There’s a probablility that the work place and the home is the same, or we can also deduce that the user might not be working. 
We can store the users temporal data in such a way we can capture the change of facts. 
- valid from
- Valid till 
- Facts
- Rule that deduce the facts 

This is excellent since we can just use it to get the facts and compress them into a model, rather than storing all of them away. We can keep a snapshot of this facts, but we do not need to store all of them (unless they are transactions).


can we add a page called downtime in Confluence, and record what happened, what we did, how we approach it, what works/what doesn’t, how long was the downtime and when it recover?

possible approach
- hide domain from public to debug (not terminate instance or swap image)
- check other services that shares the same db


## JWT
Jwt why different audience for mobile
Tracking for different devices
- Logout all feature by changing the main secret
- Logout all by checking  the issued date less than logout date
- we can handle logout from different devices with the same trick, but this requires an external distributed cache
- how to handle sessions from different devices? when the user first request the token, store all the necessary data (user agent, location etc), and every other time the user calls the endpoint with the token, track the location and check if it is possible). We can user haversine distance to calculate the user’s velocity and see if it’s possible. Walking distance, commuting, driving, cycling all has an average velocity. If we can compare the outliers, we can identify suspicious activities)
- the same concept is used for credit card, called the card velocity. 
- since we can get the unique id of the device when they logged in, we can tie the usage. This will require a lot of checking though. We can use complex event processing to monitor the changes. stream the data to a pipeline, and compare the location (if null, how should it be handled, if user did not provide the location?)
- using Subject instead of custom claims
- setting audience and issuer effectively
- exclude dynamic roles in the jwt token
- why use session instead
- should we have refresh token for applications?

todo:
- preventing thundering herd with nginx
- https://www.nginx.com/blog/mitigating-thundering-herd-problem-pbs-nginx/


## pagerank algorithm
- https://www.geeksforgeeks.org/page-rank-algorithm-implementation/
- https://www.cs.princeton.edu/~chazelle/courses/BIB/pagerank.htm
- https://searchenginewatch.com/google-pagerank-algorithm-explained
- https://hackernoon.com/implementing-googles-pagerank-algorithm-88069314fb3d

Related: how to build a search ranking algorithm using Learning To Rank
- https://www.searchenginejournal.com/build-search-ranking-algorithm-machine-learning/297047/#close

## Consistent hashing
- https://www.acodersjourney.com/system-design-interview-consistent-hashing/

implementing distributed caching
https://success.outsystems.com/Documentation/Best_Practices/Performance_Best_Practices/Improving_performance_with_distributed_caching


## Kubernetes service to service discovery
- https://kubernetes.io/docs/concepts/services-networking/service/
- https://kubernetes.io/docs/concepts/services-networking/connect-applications-service/#exposing-pods-to-the-cluster

## Complex event processing/context aware application

Real-time machine learning/fraud detection
- https://www.kdnuggets.com/2015/11/petrov-real-time-machine-learning.html
- https://stats.stackexchange.com/questions/376677/how-to-frequently-update-classification-model-with-new-training-data
- https://medium.com/codait/keeping-your-machine-learning-models-up-to-date-f1ead546591b
- https://www.oreilly.com/ideas/lessons-learned-turning-machine-learning-models-into-real-products-and-services
- https://dzone.com/articles/real-time-machine-learning-with-tensorflow-in-data
- https://towardsdatascience.com/real-time-streaming-and-anomaly-detection-pipeline-on-aws-cbd0bef6f20e
- https://towardsdatascience.com/real-time-anomaly-detection-with-aws-c237db9eaa3f
- https://databricks.com/session/real-time-anomaly-detection-with-spark-ml-and-akka
- https://dzone.com/articles/creating-real-time-anomaly-detection-pipelines-wit
- https://engineering.salesforce.com/how-we-built-an-automated-anomaly-detection-system-onto-a-streaming-pipeline-84ecfd6420e0
- https://www.information-age.com/anomaly-detection-123475833/
- https://engineering.linkedin.com/blog/2018/09/automated-fake-account-detection-at-linkedin
- https://www.datadoghq.com/blog/alerting-101-metric-checks/
- https://comtradedigital.com/fraud-detection-monitoring/
- https://en.m.wikipedia.org/wiki/Data_analysis_techniques_for_fraud_detection
- https://precognitive.io/2017/10/12/using-behavioral-analytics-detect-ecommerce-fraud/
- https://precognitive.io/behavioral-analytics/
- https://precognitive.io/device-intelligence/
- https://en.m.wikipedia.org/wiki/Data_analysis_techniques_for_fraud_detection

some ideas - combine expert system (rule based and machine learning)
- create funnels that filters responses
- use message queue/redis streams to perform transformation etc and filter when the events pass through
- design alerting/response mechanism
- check AppSensor application

Concurrent queue workers in golang. Can golang channels replaces queue?
Not really, we can make it persistent with level db (local cache) and reload the data back into the channels when the application restarts)
https://nesv.github.io/golang/2014/02/25/worker-queues-in-go.html
https://codeburst.io/diving-deep-into-the-golang-channels-549fd4ed21a8
https://www.opsdash.com/blog/job-queues-in-go.html
https://pusher.com/tutorials/messaging-queue-node-go
https://medium.com/@magicpineng/in-depth-look-at-a-scalable-robust-data-stream-processing-pipeline-using-golang-processing-500k-9e68310a0675
https://ewanvalentine.io/microservices-in-golang-part-5/
https://blog.wallaroolabs.com/2018/01/go-go-go-stream-processing-for-go/

## Distributed system design
https://medium.com/@shijuvar/building-distributed-systems-and-microservices-in-go-with-nats-streaming-d8b4baa633a2
https://blog.wallaroolabs.com/2018/01/go-go-go-stream-processing-for-go/



## hotspot prevention/thundering herd
- using golang single flight and groupcache


## Screaming architecture
https://blog.cleancoder.com/uncle-bob/2011/09/30/Screaming-Architecture.html
https://dzone.com/articles/screaming-architect
https://javadevguy.wordpress.com/2017/11/15/screaming-architect/
http://www.plainionist.net/Implementing-Clean-Architecture-Scream/
https://www.codingblocks.net/podcast/clean-architecture-make-your-architecture-scream/
https://www.freecodecamp.org/news/a-quick-introduction-to-clean-architecture-990c014448d2/
https://www.linkedin.com/learning/java-ee-design-patterns-and-architecture/what-is-screaming-architecture


Getting close. In the next version, come out with several levels of architecture. A good architecture should separate implementation from the abstraction/interface.



## microservice use case
https://dzone.com/articles/microservices-use-cases-1


## Database
Binary handling https://stackoverflow.com/questions/5801352/storing-binary-string-in-mysql
which database to choose for analytics https://www.linkedin.com/pulse/what-database-do-you-choose-analytics-shankar-meganatha
https://docs.microsoft.com/en-us/dotnet/standard/microservices-architecture/architect-microservice-container-applications/data-sovereignty-per-microservice
https://www.holistics.io/blog/should-you-use-mongodb-or-sql-databases-for-analytics/
## Database.Sharding
https://medium.com/@jeeyoungk/how-sharding-works-b4dec46b3f6


Event driven architecture
https://www.confluent.io/blog/data-dichotomy-rethinking-the-way-we-treat-data-and-services/
https://www.confluent.io/blog/journey-to-event-driven-part-2-programming-models-event-driven-architecture


## Change data capture event streaming
https://medium.com/myheritage-engineering/achieving-real-time-analytics-via-change-data-capture-d69ed2ead889


Text analytics https://www.datacamp.com/community/tutorials/text-analytics-beginners-nltk
https://scikit-learn.org/stable/tutorial/text_analytics/working_with_text_data.html


## NLP - Text Summarization
https://machinelearningmastery.com/gentle-introduction-text-summarization/

https://medium.com/m/global-identity?redirectUrl=https%3A%2F%2Ftowardsdatascience.com%2Fa-quick-introduction-to-text-summarization-in-machine-learning-3d27ccf18a9f

https://medium.com/m/global-identity?redirectUrl=https%3A%2F%2Ftowardsdatascience.com%2Funderstand-text-summarization-and-create-your-own-summarizer-in-python-b26a9f09fc70
https://medium.com/jatana/unsupervised-text-summarization-using-sentence-embeddings-adb15ce83db1
https://blog.floydhub.com/gentle-introduction-to-text-summarization-in-machine-learning/

https://www.geeksforgeeks.org/ml-text-summarization-of-links-based-on-user-query/
https://medium.com/m/global-identity?redirectUrl=https%3A%2F%2Fhackernoon.com%2Ftext-summarizer-using-deep-learning-made-easy-490880df6cd

https://www.analyticsvidhya.com/blog/2018/11/introduction-text-summarization-textrank-python/
https://machinelearningmastery.com/gentle-introduction-text-summarization/
https://catalog.ldc.upenn.edu/LDC2012T21

https://www.tensorflow.org/tutorials/keras/basic_classification

https://www.analyticsvidhya.com/blog/2018/04/a-comprehensive-guide-to-understand-and-implement-text-classification-in-python/

https://www.digitalvidya.com/blog/document-classification-python-machine-learning/
https://medium.com/mlrecipies/document-classification-using-machine-learning-f1dfb1171935
https://cloud.google.com/blog/products/gcp/problem-solving-with-ml-automatic-document-classification

https://www.kdnuggets.com/2015/01/text-analysis-101-document-classification.html
https://blog.christianposta.com/microservices/the-hardest-part-about-microservices-data/


also take a look at SQUAD standford question answering database
https://databricks.com/tensorflow/examples
https://github.com/aymericdamien/TensorFlow-Examples
https://adventuresinmachinelearning.com/python-tensorflow-tutorial/
https://www.geeksforgeeks.org/ml-text-summarization-of-links-based-on-user-query/

https://medium.com/m/global-identity?redirectUrl=https%3A%2F%2Ftowardsdatascience.com%2Fnlp-building-a-question-answering-model-ed0529a68c54
https://towardsdatascience.com/automatic-question-answering-ac7593432842?gi=dae76ddf5325
https://paperswithcode.com/task/question-answering
https://radimrehurek.com/gensim/tutorial.html
http://kavita-ganesan.com/gensim-word2vec-tutorial-starter-code/


## Monitoring/Observability

Relook into prometheus and statsd
- how to scale statsd 
- where to store data into statsd (graphite), how to stream data to graphite and how to get data out from graphite 
- setup docker version
- setup kubernetes version
- setup ui for monitoring (grafana)
- how to perform alerting and detect threshold
- how to get realtime statistics

Relook into logging with fluentd
- how to detect patterns with fluentd
- how to optimize logging
- how to send the logs to aws s3
- what tools can be used to visualize large logs data (write a custom exporter from s3 to elasticsearch)

Relook into search engine with bleeve and elasticsearch kibana etc

Tips on scaling
- scaling is about managing resources. In order to scale, we need to know the capacity of our system. In order to know the capacity of our system (request per second, cpu, memory etc), we need to measure it. Instead of relying on the system to support the given capacity that we want, we can define it ourselves by limiting them (setting the requests per second by adding rate limiter, limiting the cpu and memory etc). This allows us to have better control over the system. We can load test to determine the capacity of the system upfront. 
- if the code works, then the infrastructure is the one likely to fail(db)
- to reduce resources overhead/consumption, use caching/snapshotting. Handle the requests asynchronously, and let the client ask for the response. If the requests have not yet been processed, then we can just return a different status to indicate that it is pending processing. We can return the stale response when the system is still carrying out the processing. 
- Some killers includes sorting the whole table, or getting the total count. Joins can be a killer too when the database are sharded
- snapshot expensive operation (count) etc and periodically update them
- reduce thundering herd and hotspot keys by throttling the requests
- rate limit client apis and calls to database
- use singleflight/groupcache for caching/preventing deduplication of requests
- circuit breaker etc/ retry/ratelimit/throttling
- use asynchronous handling for expensive job
- instead of letting the client make too many requests, we can stream the data back to the client side instead, using websocker or server sent events
- the rule to caching is to determine the lifespan of the data. Is it static? then we can cache it longer. Is it dynamic, then the caching duration will be shorter. If we want real-time data, we can also look into the push approach instead of the pull approach. This could be better in some ways. 


Recommendation algorithm
- how to write one from scratch
- how to scale one
- using existing libraries
- deploying it to production
- retraining the recommendation algorithm
https://medium.com/arc-software/recommender-systems-behind-the-scenes-a39c831a0ae2
https://towardsdatascience.com/prototyping-a-recommender-system-step-by-step-part-1-knn-item-based-collaborative-filtering-637969614ea
https://en.m.wikipedia.org/wiki/Recommender_system#Content-based_filtering
https://en.m.wikipedia.org/wiki/Tf–idf
https://en.m.wikipedia.org/wiki/SMART_Information_Retrieval_System
https://en.m.wikipedia.org/wiki/Latent_semantic_analysis
https://en.m.wikipedia.org/wiki/Latent_Dirichlet_allocation
https://www.kaggle.com/pierremegret/gensim-word2vec-tutorial
https://www.kaggle.com/pierremegret/gensim-word2vec-tutorial


## Data Science

- https://www.textkernel.com/challenges-behind-parsing-matching-cvs-jobs/
- https://www.freelancer.com/projects/data-mining-matlab-mathematica/nlp-resume-parser-write-nlp/
- https://datascience.stackexchange.com/questions/36447/resume-parsing-extracting-skills-from-resume-using-machine-learning
- https://medium.com/@divalicious.priya/information-extraction-from-cv-acec216c3f48
- https://dataturks.com/blog/named-entity-recognition-in-resumes.php
- https://medium.com/activewizards-machine-learning-company/top-9-data-science-use-cases-in-media-and-entertainment-a5705231e228
- https://bigdata-madesimple.com/6-of-my-favorite-case-studies-in-data-science/
- https://medium.com/coriers/7-use-cases-for-data-science-and-predictive-analytics-e3616e9331f9
- https://blogs.sas.com/content/hiddeninsights/2015/05/28/building-customer-profiles-in-the-era-of-big-data/
- https://arxiv.org/pdf/1503.07474.pdf
- https://medium.com/datadriveninvestor/represent-users-and-products-in-a-data-science-way-for-e-commerce-website-22d7dbc24c33


## Consistent Hashing

https://quabase.sei.cmu.edu/mediawiki/index.php/Shard_data_set_across_multiple_servers_(Consistent_Hashing)


## API Design
https://nordicapis.com/could-artificial-intelligence-improve-api-design/


## Deep learning use case

What are the use cases of AI, and what can be applied? 
https://skymind.ai/wiki/use-cases


## Change Data Capture CDC 

Look into how to use change data capture to capture facts (data that has been successfully stored in the database.
This is perhaps a better (?) solution than streaming the results once the operation completed at the application layer because there can be some fields (autogenerated id from database) that cannot be obtained from the application layer.
(?) but if the insert fail, we might still need to publish the events saying that the operation failed.
- but at least we don’t need to deal with changes from the application side
- how do we handle schema changes in the database? or addition of new tables?


https://debezium.io/blog/2016/08/02/capturing-changes-from-mysql/
https://vladmihalcea.com/a-beginners-guide-to-cdc-change-data-capture/
https://medium.com/fundbox-engineering/https-medium-com-fundbox-engineering-diy-cdc-pipeline-from-mysql-to-snowflake-32c14b705cfe
https://medium.com/myheritage-engineering/achieving-real-time-analytics-via-change-data-capture-d69ed2ead889
https://www.percona.com/blog/2016/09/13/mysql-cdc-streaming-binary-logs-and-asynchronous-triggers/
https://vladmihalcea.com/how-to-extract-change-data-events-from-mysql-to-kafka-using-debezium/
https://engineeringblog.yelp.com/2016/08/streaming-mysql-tables-in-real-time-to-kafka.html
http://shzhangji.com/blog/2017/08/12/extract-data-from-mysql-with-binlog-and-canal/
https://www.bouvet.no/bouvet-deler/utbrudd/a-simple-todo-application-a-comparison-on-traditional-vs-cqrs-es-architecture
https://medium.com/@pierreprinetti/event-sourcing-in-go-the-event-handler-29f9438c58f0
https://medium.com/@shijuvar/building-microservices-with-event-sourcing-cqrs-in-go-using-grpc-nats-streaming-and-cockroachdb-983f650452aa
https://outcrawl.com/go-microservices-cqrs-docker/


## Document Classifier

- An API to read the input file
- How to parse PDF? extract the text from pdf, and go through the pipeline.  (note, pdf is only a source, we should create an interface that accepts a string, since the source can be from anywhere, input string, word text, pdf, excel, scraped website)
- lowercase text, tokenize text, remove stopwords, stemming, lemmatization
- NER analysis
- parse the section
- how to find the skills and section
- how to parse different type of documents (word, docs, pages)

- with this, we can first perform tagging on the documentation and tfidf. we can allow search to be done, 
- e.g. show me the resumes with the skills javascript
- show me the users with 10 years experience
- this requires knowledge on NLU natural language understanding (take a look at SpaCy)

https://www.analyticsvidhya.com/blog/2017/01/ultimate-guide-to-understand-implement-natural-language-processing-codes-in-python/

come up with a simple POC first, use jupyter notebook to execute the independent pipeline, then only look into optimization for each steps
at the end release a simple api or grpc that allows the code to be streamed (redis stream?) to be analyzed real-time.
- this can be a worker process and we want to do it once only/can also run as a cron daily, but best to process it real time)
- we can create a basic search engine with the text that is scraped
- create a simple visualization/website to display each pipeline steps



Example streaming
- store the last N values in the given time window
- when there are new values that exceeds the size N, remove the head and push to the array
- compute the last activity
E.g. when checking the user’s location
user {
	lat, lng, timestamp
}
- skip zeros/invalid location lat/lng
- we don’t need to store all the values, just compare the previous value with the latest one
- delta distance / delta timestamp > in valid range
- user has moved to an invalid duration


## Stream Processing

https://wso2.com/library/articles/2018/02/stream-processing-101-from-sql-to-streaming-sql-in-ten-minutes/
https://medium.com/stream-processing/what-is-stream-processing-1eadfca11b97
https://www.toptal.com/mobile/context-aware-apps-and-complex-event-processing

https://calcite.apache.org/docs/stream.html



POS Tagger 
What can we do with tagger?

What types of tagger are available?
- rule-based pos taggers (brill tagger)
- stochastic pos taggers (using hidden markov model)


- brill tagger. An “error-driven transformation-based tagger”. A form of supervised learning.
- Standford log-linear part of speech tagger: http://www.nltk.org/api/nltk.tag.html#module-nltk.tag.stanford




## Algorithms 
How to use HMM in the real world
how to compute viterbi algorithm in different languages
- this can be used for content generation, chat bot
- https://www.freecodecamp.org/news/a-deep-dive-into-part-of-speech-tagging-using-viterbi-algorithm-17c8de32e8bc/


## Authorization
- how does authorization works for offline application?
- how to split the application into hybrid offline/online solution? read only data can always be offline. If we want to create data etc, we can perform it locally first, then sync the data later when we are online(?) will this cause a hotspot issue, when all offline devices went online at the same time.
- how to ensure the files created offline are batched before synced online (especially when there are plenty of files)
- the idea of putting things offline is to save the network calls to the server, hence reducing server load and making the application more responsive.
- syncing server like dropbox is what we need. But how do we design it? We can queue the requests on the client side and then fire them when they are back online. We need to ensure the calls are not rapid to prevent own ddos. Another alternative is to set a rule that only online clients can upload content.


## Deployment

how to handle zero downtime deployment

https://www.ebayinc.com/stories/blogs/tech/zero-downtime-instant-deployment-and-rollback/
https://www.exoscale.com/syslog/kubernetes-zero-downtime-deployment/
https://blog.pvincent.io/2018/12/patterns-for-zero-downtime-deployments-of-large-applications/


A good leader is one who can make decision, and reflect upon it and undo it if the decision does not feel right.


List down all useful books here

Idea. Find error in text or grammar, use gamification. But doing translation behind the scene

Put the questions you want to ask
How to create real time streaming architecture
Update machine learning model in real time

Say, if we want to create a credit card fraud detector, we need to design a model. There are only two possible outcome the model can give us
- a definite answer
- A probabilistic one. 
The former is when we know exactly that a credit card is flawed. It is a fact, and does not require any machine learning whatsoever. The latter is more in a prediction.


Handling multilingual for gaoling including errors and content 
Dynamic forms, good or bad?
A/b testing using hashing the user id modulo

Simplest sync server
- The initial idea is to hash the data using md5 and compare the hash of the data on the server against the client. But then hashing again is computationally expensive.
- The second idea is to check the last updated time. In mysql, we can always set the updated at date time to update whenever there is a change.
- On the client side, if they are offline, then just push the items to be updated in a local queue/database. When the app is back online, then update it. There can only be a max of 10 items to be updated when it is offline. 
- The logic to update is as follow: The content can only be updated if the created at date (t0) of the content of the client is greater than the updated at date (t1) of the content on the server side and t0 is less than NOW. This is to avoid having the content to be overwritten by the stale  data (e.g. is user is offline on the mobile, and has a content that has not yet been synced online. The user update the content on the web, and then goes online on the mobile. The mobile content should not be synced, since the server already has the latest content.
e.g.

User is online. User create book {date: 1 Jan 2019, updated_at: 10:00pm}.  User goes offline.
User is offline. User update book {date: 1 Jan 2019, created_at: 10:11pm}. User goes online.

if book_local.created_at > book_server.updated_at:
	can_update

Grammar corrector. Enter a sentence you want to validate the correctness.
User can submit the corrected version, others can Like or dislike.

Private eye. Search for something or someone. from just a picture.

When to use NATs vs Redis Stream vs Kafka. One of the primary reason is the reusability. For example, go nats does not have clients in certain languages, while redis is almost available everywhere.



todo: use content enricher concept
- also, rather than real-time recommendation, store the results of the recommendation before sending them out. Use streaming to ensure that the data can be replayed


Why does YouTube pause the video play after a while? Maybe because they have complex event processing to determine the users activity - active, idle, picky(when they click another link before the first video payback is completed) etc.

Why does Facebook like still works when it’s offline? Because they debounce it. There’s no merit in showing real time like counter since it can be taxing fro performance. Thus it is better to only make the call after user is idle, his also prevents abuse on the system.

Why does grab shows finding for driver? It’s basically an asynchronous process working to match the drivers in the background based on the current location, whether the driver has accepted the request, or whether the driver has sufficient rating to be recommended. Note that it’s not necessary the first driver that would be selected. A bunch of drivers can first accept the passenger, then the algorithm will decide if they can take the passenger based on the rating. 







Learn envoy, and all the functionalities, with docker, kubernetes, rate limiting and then setup with grpc mysql redis etc. Learn back linkerd tutorial.



Consul envoy service discovery


Setting up the data science stack
- before starting with machine learning, we need to setup the infrastructure for data gathering first, aka enablers. 
- We also need to find out what data can be captured, aka active data collection. The passive data collection strategy is to collect all and making sense of them later. 
- It’s better to set a target result, what kind of data is required to produce the desired output. 
- create a playbook for metrics and experiments, such as
Experiment
- valid_from
- valid_till
- results
- description
- target_achieved
- comparison
- conclusion

how to track user activity across different devices and time?
we can use bitmap to track user’s daily and hourly records
- weekly: [sun, mon, tue, wed, thu, fri, sat] days
- daily: [0…23] hours
From here we can find the most common day that the user login, and the most frequent time that the user is online. If we gather this enough for a month, we can have the data average presented.
How long should the data be kept? Probably 1 month old, so what we will do is collapse the old data counts 

Find the most visited site for each user. and from there we can infer if the content is what they need.

users_most_visited_pages: []
users_most_online_time: []
users_average_time_on_device: []
users_time_taken_to_complete_process… (can be a good measure for forms etc, to improve the form design etc)
users_most_searched_keyword: []

how_does_ab_testing work?


Database design:
- use binary id for all dynamic entries. For user, add an additional id that is auto incremented, so that we can use it for testing.
- 

Music player for the deaf - through vibration/visualization
Digital will for the dead - a message that can only be opened in the future
digital assets - user’s that are popular (reviewer. vlogger, celebrity can have collateral assets, which are their users and also the likes, comments etc). Provide loans to users through with their digital assets as collateral.

Viral factor calculator - calculates the net worth of a social media celebrity. Also includes recency (newest comments/feeds will have higher score) and the success rate of the merchants they promote.

Recommender system algorithm + hot rank algorithm. Incorporate recency into the recommender engine so that newer items will be ranked higher than older ones. Why is this important? Some products (such as events/promotion etc) has expiry time and is valid only for a certain period. Others, such as movies/songs are seasonal - they follow a certain trend and usually according to the time. So it might be more reasonable to recommend songs now than songs in the 50s even if the similiarity score is higher.


Learn about Facebook Pixel and Google Analytics tracker to capture informative data from the website. Do a sample ecommerce testing and see hwat user clicks the most? Check if the solution can be incorporated with A/B testing and also bandit algorithm.


Separate interface from concrete implementation.


https://www.datacamp.com/community/tutorials/probability-distributions-python

Learn about segment trees: https://hackernoon.com/practical-data-structures-for-frontend-applications-when-to-use-segment-trees-9c7cdb7c2819


also, time to update the projects selection and probably host them. Update resume format to display the format too

Github Recommender: displays a list of top github users with recommendation. Skills proven: data recommendation for users, data scraping and data visualization.
learn to


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



## Complex Event Processing

https://www.toptal.com/mobile/context-aware-apps-and-complex-event-processing


## NLTK 

https://www.nltk.org/book/ch01.html#sec-automatic-natural-language-understanding

https://stackabuse.com/text-summarization-with-nltk-in-python/



## Scaling

https://medium.com/@evyborov/scaling-up-to-your-first-10-million-users-summary-aws-summit-sf-2017-819dcf532fb7


## Building neural network from scratch


https://towardsdatascience.com/how-to-build-your-own-neural-network-from-scratch-in-python-68998a08e4f6



Git commit messages
- feat: A feature that is visible to end users
- fix: A bugfix that is visible for end users
- chore: A change that doesn’t impact end users (e.g .changes to CI Pipeline)
- docs: A change in the README or documentation
- refactor: A change in production code focused on readability, style and / or performance

## Message Queue

https://www.codemotion.com/magazine/kai-wahner-build-a-scalable-infrastructure-with-apache-kafka-1247
https://cloudblogs.microsoft.com/opensource/2018/07/09/how-to-data-processing-apache-kafka-spark/
https://hackernoon.com/distributed-log-analytics-using-apache-kafka-kafka-connect-and-fluentd-303330e478af?gi=81e296c44344
https://www.confluent.io/blog/using-apache-kafka-drive-cutting-edge-machine-learning
https://blog.rapid7.com/2013/12/18/5-uses-for-log-data-that-you-never-thought-of/
https://www.fastly.com/blog/7-business-uses-for-logging


## Web Workers

https://hackernoon.com/web-workers-in-react-redux-application-129274e84a4e
https://auth0.com/blog/speedy-introduction-to-web-workers/

https://bitsofco.de/web-workers-vs-service-workers-vs-worklets/
https://developers.google.com/web/updates/2018/08/offscreen-canvas
https://www.freecodecamp.org/news/how-web-workers-can-help-with-consistent-asynchronous-tasks-in-javascript-cd6d728fa4ee/


## Python GUI Tkinter example

## Python multithreading

What are the different kind of concurrency options available in python?
How to implement them in the big data applications.


## Interesting data blog

http://datagenetics.com/blog.html
http://datagenetics.com/blog/october32018/index.html


## Feature toggle

Do some sample repos that shows how to perform feature toggle

https://blog.codecentric.de/en/2019/02/feature-toggles-benefits-drawbacks/


## Golang cookie

https://www.sohamkamani.com/blog/2018/03/25/golang-session-authentication/
https://gowebexamples.com/sessions/


## Matrix Factorization

https://en.m.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)
http://rstudio-pubs-static.s3.amazonaws.com/335300_11d40bf12d8940f78d9661b3c63150dc.html

https://www.freecodecamp.org/news/singular-value-decomposition-vs-matrix-factoring-in-recommender-systems-b1e99bc73599/

## Segment Trees

https://kartikkukreja.wordpress.com/2014/11/09/a-simple-approach-to-segment-trees/

https://codeforces.com/blog/entry/15890
https://hackernoon.com/practical-data-structures-for-frontend-applications-when-to-use-segment-trees-9c7cdb7c2819
https://cp-algorithms.com/data_structures/segment_tree.html
https://www.hackerearth.com/practice/data-structures/advanced-data-structures/segment-trees/tutorial/
https://medium.com/m/global-identity?redirectUrl=https%3A%2F%2Fblog.mapbox.com%2Fa-dive-into-spatial-search-algorithms-ebd0c5e39d2a

## Building a recommendation engine

https://www.codeproject.com/Articles/1232150/Building-a-Recommendation-Engine-in-Csharp
https://stackoverflow.com/questions/2323768/how-does-the-amazon-recommendation-feature-work
https://medium.com/netflix-techblog/netflix-recommendations-beyond-the-5-stars-part-2-d9b96aa399f5

Case based reasoning CBR: https://en.m.wikipedia.org/wiki/Case-based_reasoning
https://www.quora.com/What-are-examples-of-rule-engines-combined-with-machine-learning



## Python data hacks

https://towardsdatascience.com/10-simple-hacks-to-speed-up-your-data-analysis-in-python-ec18c6396e6b

## Data warehouse 

http://tdan.com/data-warehouse-design-inmon-versus-kimball/20300

## Viterbi / HMM

https://www.freecodecamp.org/news/a-deep-dive-into-part-of-speech-tagging-using-viterbi-algorithm-17c8de32e8bc/
https://pkghosh.wordpress.com/2013/10/06/predicting-customer-loyalty-trajectory/

https://dzone.com/articles/how-do-you-measure-if-your-customer-churn-predicti
https://towardsdatascience.com/hands-on-predict-customer-churn-5c2a42806266
https://stats.stackexchange.com/questions/31746/what-is-the-difference-between-the-forward-backward-and-viterbi-algorithms
http://www.blackarbs.com/blog/introduction-hidden-markov-models-python-networkx-sklearn/2/9/2017
http://www.adeveloperdiary.com/data-science/machine-learning/introduction-to-hidden-markov-model/


## Data analytics gathering

https://support.google.com/analytics/answer/1033068#See
https://arxiv.org/pdf/1811.03402.pdf
https://towardsdatascience.com/how-to-build-a-data-set-for-your-machine-learning-project-5b3b871881ac


## Machine learning usecases

- google search makes use of ML and query understanding, answer models
- photo tagging for people and objects - google search, facebook, pinterest
- content recommendations = amazon, netflix, facebook, youtube
- video tagging, caption - youtube, facebook
- spelling, grammar checking, translating
- games 
- ads targeting
- recipe cooking recommendation based on the ingredients you have


## Scraping best practices

- tools
- what headers to use (why)
- how to rotate proxy (why)

https://realpython.com/tutorials/web-scraping/
https://medium.com/velotio-perspectives/web-scraping-introduction-best-practices-caveats-9cbf4acc8d0f
https://www.codementor.io/blog/python-web-scraping-63l2v9sf2q
https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/
https://www.scrapehero.com/how-to-rotate-proxies-and-ip-addresses-using-python-3/

