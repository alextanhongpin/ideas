# Ideas



## Docker Monitoring

Done this before, but didn't write down the steps for others to replicate. Also, there are some improvements that I want to, like generating daily, weekly, monthly and yearly report on the metrics (CPU usage, memory, SLA etc).

Pair it with Grafana and Prometheus.



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


## Actively Pursuing

- Site Reliability Engineering
- Languages: Haskell, Rust, Scala, Nim, Python 3.7, NodeJS, Elixir
- Infrastructure: Linkerd 2.0, Consul 1.2 Service Mesh, Terraform, Kubernetes Operators
- Blockchain: White papers
- Data structures and algorithm: https://en.wikipedia.org/wiki/Ford%E2%80%93Fulkerson_algorithm


## LXC, LXD and HyperContainer

Only works on linux for now.
https://docs.hypercontainer.io/index.html


Also other alternatives like kata container, virtlet etc


## Kiali

https://github.com/kiali/kiali

Observations using kiali and opentracing, it doesn't have to be real-time. They are basically gathering metrics through different means (e.g., prometheus). It is always good to be able to time-travel back at the time some incident happen. Also, https://opencensus.io/introduction/




## Solving Docker Image issue

Sometimes the new application that we are deploying is not working (especially in AWS, when adding new environment variables), and it will keep crashing in an infinite loop. Solution is to deploy a dummy nginx instead of our complex application, cause it will just display the dummy 504 page. A better alternative is to create a custom server that display a dummy 500 page.



## Meta Tags

In html, you can get more information from users through click analysis. But just clicking the region would not give much indication on what the user like. So, it's probably interesting to inject metadata to each elements, metadata that contains much more information that is obtained either manually or through machine learning.

## Learn about fuzzy testing

https://en.wikipedia.org/wiki/American_fuzzy_lop_(fuzzer)

In golang, the `quickcheck` package can be used to do testing too.




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




## MutationObservers, WeakMap, WeakSet JS, CustomElements

Also sharedWorker with websocket. https://blog.pusher.com/reduce-websocket-connections-with-shared-workers/

Build your own approach to designing components without framework.



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


## Stuff to learn

- learn crystal/rust programming language basic and work on a simple project
- linkerd 1.6 and 2.0 updates 
- find out how to do consistent hashing in different languages (golang, nodejs, python etc)
- learn more about message queue use cases and how to implement production-ready message queue
- relook into design patterns for different languages, and microservice architecture and system design.


## Write the three principles

## TODO: Graphql

- handling table joins
- querying with different data sources (mysql)
- access controll list
- authorization
- where does business logic reside? Probably used graphql as a read-only data source


## Golang struct order
https://medium.com/@felipedutratine/how-to-organize-the-go-struct-in-order-to-save-memory-c78afcf59ec2


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
- Group watch with Netflix idea, share the same subscription but pay in group
- Group forms honestbee
- OWASP Top 10, and how to secure your login form.
- Project setup by just using environment variables. The idea is to have a container that initialises all the basic micro service components such as database and message queue, config loading etc. Then we can just set the environment variables to use those infrastructure. The user may choose to extend the container to add new configuration. The idea is similar to go-kit. Rather than providing user options to fill up, we just define the environment variables that the user have to fill in.

Active service pattern is just a cron job. How to pull data periodically? Return the last update date. MD5 hash the content, or check if the updated date is greater than the previously updated data. If you are pulling a collection, then the greatest last updated date is the indicator.

## Useful patterns for data
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






Related: how to build a search ranking algorithm using Learning To Rank
- https://www.searchenginejournal.com/build-search-ranking-algorithm-machine-learning/297047/#close




Getting close. In the next version, come out with several levels of architecture. A good architecture should separate implementation from the abstraction/interface.


## Database
Binary handling https://stackoverflow.com/questions/5801352/storing-binary-string-in-mysql
which database to choose for analytics https://www.linkedin.com/pulse/what-database-do-you-choose-analytics-shankar-meganatha
https://docs.microsoft.com/en-us/dotnet/standard/microservices-architecture/architect-microservice-container-applications/data-sovereignty-per-microservice
https://www.holistics.io/blog/should-you-use-mongodb-or-sql-databases-for-analytics/

## Database.Sharding
https://medium.com/@jeeyoungk/how-sharding-works-b4dec46b3f6









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



## how to track user activity across different devices and time?
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

Learn about Facebook Pixel and Google Analytics tracker to capture informative data from the website. Do a sample ecommerce testing and see hwat user clicks the most? Check if the solution can be incorporated with A/B testing and also bandit algorithm.


Separate interface from concrete implementation.


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


## Feature toggle

Do some sample repos that shows how to perform feature toggle

https://blog.codecentric.de/en/2019/02/feature-toggles-benefits-drawbacks/


## Golang cookie

https://www.sohamkamani.com/blog/2018/03/25/golang-session-authentication/
https://gowebexamples.com/sessions/



## Scraping best practices

- tools
- what headers to use (why)
- how to rotate proxy (why)

https://realpython.com/tutorials/web-scraping/
https://medium.com/velotio-perspectives/web-scraping-introduction-best-practices-caveats-9cbf4acc8d0f
https://www.codementor.io/blog/python-web-scraping-63l2v9sf2q
https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/
https://www.scrapehero.com/how-to-rotate-proxies-and-ip-addresses-using-python-3/

