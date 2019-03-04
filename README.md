# Ideas

## Identifying user's personality through conversations

How can we understand the user's personality and tie them to the brigg-myers personality test?

1. From the conversation, check the frequency of the most commonly used words.
2. Check the length of the conversation. Short conversation means more close, longer means more open etc.
3. Check the response time - how fast they reply your message.
4. Check the continuation of the conversation - how many replies they will take before they stop.

## Prevent scraping through pagination token

Numeric pagination is easy to scrape `?limit=9999&offset=1`. Find a way to create a pagination token that is hard to scrape.

Also, do not expose `id` of resources to the frontend. That includes pages that displays a single item and so on e.g. `books/:id`. Rather, use slug instead as identifier.

## Create a simple page for voting

Use websocket that allows clients from different devices to connect and vote.

Ensure that one person can only vote once from the device.

## Reverse Engineer MultiWorld Testing

Start with a simple bandit experiment, understand the limitation (delayed response). Add real-time graphs and intelligent bot to tell you what can be optimized.

## Smart bots with different personality

Create a bot that has different personality (features). Allows users to search through something and create alerts.

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

## User Recommendations

Compare the different recommendations approach and look into matrix factorization. 

## Bandit Server

Bandit algorithm application in recommendations and other things. Not the concurrent issue with some algorithms (greedy epsilon) which requires the values to be updated immediately - imagine many users are pulling the same arm at the same time when the algorithm has not been updated.

Also look into how to apply contextual bandit by using decision tree.

## Retry Pattern and Circuit Breaker

Design a retry pattern and circuit breaker that can be reused. It will be using exponential backoff when performing retry.

## Databases

Distributed sqlLite with Bedrock, CockroachDB, TiDB.


## Tracing

Carry out opentracing with Node and python. Also experiment with X-Ray trace.


## Imbalanced Dataset Machine Learning

Reference [here](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwi2_ISImcXXAhUBLY8KHaS9BkAQFggxMAE&url=https%3A%2F%2Fwww.analyticsvidhya.com%2Fblog%2F2017%2F03%2Fimbalanced-classification-problem%2F&usg=AOvVaw18t2VQ8g39iZnlFc8a7O4t) and [here](https://machinelearningmastery.com/tactics-to-combat-imbalanced-classes-in-your-machine-learning-dataset/).

## CQRS and Event Sourcing

Look into how CQRS and Event Sourcing can be implemented. Also look into how Git versioning works.

What is CQRS? How can I build and test each components of event sourcing while scaling it. Check the implementation for event sourcing using Go, Nodejs, Elixir and Scala.

## Sudoku Solver

Look into how to solve sudoku uisng the `Dancing Links` and `Algorithm X` algorithms. Working solution with TypeScript [here](https://github.com/alextanhongpin/algorithm-x).

## Relevant Search

Normal search will not do for most cases - try to incorporate context into the search. At the same time, try to add personalization to the search.

Most list pages will display a list of items in the first place. While it's possible to just display them based on the last created date, it doesn't add relevancy to users that has searched for something, and want to search for similar things. So, keep track of what the users have searched for, and then use the last history to compute the personalized search. It would be great to keep another section to recommend users something related to what they have searched for.


## Singleflight pattern

Look into the singleflight pattern for subscribing to connection. http://www.cs.duke.edu/courses/cps296.4/fall13/838-CloudPapers/dean_longtail.pdf. Also look into connection pooling in Golang, and sync.Once.

## Future of Web Apps

How would the future of web apps look like? Design conceptual websites with modern technologies.

## ACL Admin

ACL that allows you to limit user's access to certain operation (read, write, etc) and allow you to invite new users through email. Basic implementation with nodejs [here](https://github.com/alextanhongpin/node-scope).


## ABAC and RBAC

Implement Attribute Based Access Control (ACAB) and Role Based Access Control (RCAB) for different languages.

## Chat Server

Create a full chat server. The server is written in [golang](https://github.com/alextanhongpin/go-chat) and the client [Vue](https://github.com/alextanhongpin/vue-chat). Work in progress.

## Bloom Filter

The classic example is using bloom filters to reduce expensive disk (or network) lookups for non-existent keys. Another use case is to check if the unique username existed before allowing users to choose that username. Repo [here](https://github.com/alextanhongpin/bloom-filter).

## Markov Chain Classifier

Predicting user behaviour using transition probability. Can also be used to predict customer conversion (perhaps to find out the churn possibility).

## Spam Filtering

Use naive bayes to predict if a text is spam or not.

## Boosting algorithm

AdaBoost.


## Named Entity Recognition

Learn and understand the use case of NER. Use NER to understand the context of the word - perhaps optimise it so that it can be used to perform more relevant search and deliver a google-like search experience.

- examples
- how to train your own model
- architecture deployment

Repo [here](https://github.com/alextanhongpin/standford-ner-basic).

## Levenshtein Distance

Understand how to implement dynamic programming with it.

## AutoCorrect

Norvig's autocorrect. http://norvig.com/spell-correct.html

## LambdaMART

Understand the LambdaMART algorithm and use it to create ranking system.

## Viterbi Algorithm

Checkout Viterbi algorithm, and see what are the applications in real life. Repo [here](https://github.com/alextanhongpin/hidden-markov-model).

## Technical Indicators

Try out all the possible technical indicators and write the algorithm in Python Jupyter. Also, run it against a real test data, plot it out and visualize the outcome. See if they can be used for prediction. Also, check if you can do image pattern matching against the popular technical indicators. Repo [here](https://github.com/alextanhongpin/technical-indicators)

## Decentralized Applications

Check out how to create and deploy a simple dapp. Also, check out solutions for distributed databases. 

## Regression with Stochastic Gradient Descent

You can do linear regression with stochastic gradient descent. Understand the difference between the ordinary solution and the solution using stochastic gradient descent.

## Affinity Analysis

Compare the different data mining algorithms for affinity analysis, especially apriori and eclat. Repo [here](https://github.com/alextanhongpin/affinity-analysis).

## Minimal Docker images

For rust, haskell, golang, node, scala and python. Write down the size and multi-stage build process.

## CRISP-DM

Cross Industry Standard Practice for Data Mining. Try to implement the full steps.

## Contextual Bandit

Learnm and apply the contextual bandit algorithm.

## Ad Click Prediction

Can be done through several ways - such as logistic regression. Find out how to implement a working server for that.

## Dynamic Pricing and Price elasticity

Find out how to work with time series data for prices, and the differences between dynamic pricing vs price elasticity algorithms and how to apply them.

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

## JSON API Specification

Look into JSON API specification and understand how to implement it correctly.

## Avro Schema

Look into avro schema registry and compare it against protobuf.

## Hidden Markov Model

Implement hidden markov model in different languages.

## Keras Text Processing

Look into the different areas of text processing and understand how to apply keras to it. Also look into Spacy for chatbots and learn how to dockerize them.

## Frequent Itemsets

Use frequent itemsets for food recommendation, create packages (food, drink and misc.), log the most frequently purchased and perform recommendations.


## New Search

Rather than focusing on letting users search on a keyword, provide dynamic recommendations - listing page that changes over time based on the frequency and trend. Users can still search for stuff based on keywords, but this will be the primary feature.

## Yik Yak

Make an app like Yik Yak, that will messages that will expire after certain days. Also, add sentiment analysis to create postive text rather than negative.

## Service Value

Defining Service value will enable easy rewrites of the API.

## Evolutionary Microservices Architecture

While working on a notification delivery system, we came up with different versions of the services. The services are broken up into several microservices, and most of the time we need to work on optimizing them (rewrite in other languages etc.). But a lot of time is wasted carrying out performance testing to identify which version is better (higher request rate, lower latency etc.). The idea is to take the concepts of genetic programming to discover the strongest candidate.


## gRPC Healthcheck

## WebSub

Look into websub and how to implement it.

## Istio/Conduit/Linkerd/Nomad

Learn the basics of Istio and Conduit and create examples. Also look back into Nomad and Linkerd.


## System API, Experience API and Process API

https://www.mulesoft.com/sites/default/files/resource-assets/API-led-connectivity-new-soa-updated.pdf

Try to understand the separate layer and why they exist. Is it also possible to abstract, say database access calls to one layer, and reduce the side-effects by splitting read/write (CQRS), which can only be consumed through RPC by other clients?

## Exposing schemas

Given a hypothetical api endpoint `/foods` which return foods, we can have an equivalent schema endpoint `/schemas/foods` that returns the JSON Schema of the resource.

## Intelligent API as a Service

Spam, NER, Search, Viterbi, Markov Chain, Bandit, Recommendation, Sentiment Analysis API for real-world use cases.


## Elasticsearch Syncing with MySQL and MySQL Migration

Utilise CDC (change data capture) to sync data from MySQL/Postgres to Elasticsearch. Check to ensure how they handle schema changes (removal/addition of new columns) and creation of new tables as well as deletion.

If there are constraints, set the rule to allow only addition, not removal of columns. Deprecate it and warn end users about it. If there are fields that are rapidly changing but does not require indexing, store the data as a json object in a new column. Else, just use nosql.

To prevent users from performing addition/deletion, create a new user and limit the access.

## Separate Read/Write

Read and writes should be separated in the microservices layer, as they can be scaled independently. Besides, it is easier to control the side-effects and make the system more maintainable (write services requires more attention). The database access can be separated too, and since write is only to the master, the creation of user in slave is only for read access.

## Service Migration

If there are new services with changing schemas, the idea is to deprecate the older version. It will still be running, but warn the end users about the deadline and the necessary changes for the newer version. Also, log the requests count together with the version to see how many people are still consuming the endpoint. Once the count reach below certain threshold, deprecate it completely. To make the migration transparent, one can apply the proxy or adapter pattern.

## Microservices Approach

- what microservices to build? video? check for existing schemas in schema.org (DRY)
- what cloud design pattern is involved? basically how to handle scaling in the future
- what technology stack to use (no debate here, but it's good to be clear on this - use the right tool)
- simple mvp and test cases
- what data needs to be analysed

## Planning Large Terraform Projects

- how to setup workflow for different environment (production, staging, etc)
- how to test the setup?
- how to manage chain workflows (creation of one resource requires details from another resources) without coupling them


## Versioning Application

How to measure performance changes when versioning application? Every release (new features) will definitely slow down the application. How to detect the threshold that is allowed? Possibly through prometheus, find a way to inject the version of the application, then plot the graph through grafana.

## Traffic Shifting

It is possible to do traffic-shifting - but can we shard (duplicate) the calls to a staging environment instead to debug/test performance/check errors? When doing so, it is important to isolate side-effects (writes to db, sending out emails, triggering webhook etc). Find out how. 

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

## Chaos Monkey Testing

The idea of terminating instance is not difficult. But integrating resiliency to services is the main idea behind chaos monkey testing. Are there better ways to integrate it? Here are some things that can be considered when writing services:

- what happens when the database is down?
- what happens when a service call fails (retries, circuit breaker)?
- what happens when the infra fails (cache, config)?
- what happens when the wrong configuration is passed in?
- what happens when the database is empty?
- how to plot the graph of relationship between services?

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

## Basic API Server Information

Should probably return more meaningful information for backend services at the index `/` endpoint:

```js
{
  "language": "go version 1.10", 
  "build_type": "docker" // or binary
  "build_date: "2018-07-11T10:12:33Z",
  "version": "4a2690e",
  "deployed_date": "2018-07-11T10:12:33Z"
}
```

## Slicing a monolith

### Config

Config can be divided to a few categories:
- application config, prefixed with `APP_`, e.g. APP_VERSION, APP_HOST, APP_PORT
- infrastructure config, like database or message queue, e.g. DB_HOST, NATS_HOST, etc
- service config, for feature toggle, crontabs, etc
- dependencies, such as logger settings in different environment

When you have a lot of config, things can get pretty messy. Some of the key pointers for each config is to:

- document the usage
- make the source explicit (e.g. where to find them)
- set defaults

Configs are typically centralized in a single file. Why not break them down instead to different files or place them in their respective module folder?

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


## Look into Affinity Analysis
Also, there are some good stuff on high-utility itemset mining. Probably take a look into that.

## IDM (Internet Downloader Manager)

Create a basic version of internet downloader manager.

## Look into distributed synchronization protocols and implement a basic working example

## Look into NATS

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


## Create a name generator

Markov chain can be used to generate random names:

http://pcg.wikidot.com/pcg-algorithm:markov-chain

Also, the way docker names are generated is plain simple.

https://github.com/moby/moby/blob/master/pkg/namesgenerator/names-generator.go

https://www.biographyonline.net/people/famous-100.html
https://en.wikipedia.org/wiki/List_of_programmers
https://en.wikipedia.org/wiki/List_of_Pok%C3%A9mon
https://jobmob.co.il/blog/positive-personality-adjectives/

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
