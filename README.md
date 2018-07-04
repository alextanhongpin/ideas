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

Look into how to solve sudoku uisng the `Dancing Links` and `Algorithm X` algorithms.

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

The classic example is using bloom filters to reduce expensive disk (or network) lookups for non-existent keys. Another use case is to check if the unique username existed before allowing users to choose that username.

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

## Levenshtein Distance

Understand how to implement dynamic programming with it.


## LambdaMART

Understand the LambdaMART algorithm and use it to create ranking system.

## Viterbi Algorithm

Checkout Viterbi algorithm, and see what are the applications in real life.

## Technical Indicators

Try out all the possible technical indicators and write the algorithm in Python Jupyter. Also, run it against a real test data, plot it out and visualize the outcome. See if they can be used for prediction. Also, check if you can do image pattern matching against the popular technical indicators.

## Decentralized Applications

Check out how to create and deploy a simple dapp. Also, check out solutions for distributed databases. 

## Regression with Stochastic Gradient Descent

You can do linear regression with stochastic gradient descent. Understand the difference between the ordinary solution and the solution using stochastic gradient descent.

## Affinity Analysis

Compare the different data mining algorithms for affinity analysis, especially apriori and eclat.

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
- nettrace, openzipkin, opencensus

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
