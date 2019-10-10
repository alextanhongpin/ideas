# Ideas

## Docker Monitoring

Done this before, but didn't write down the steps for others to replicate. Also, there are some improvements that I want to, like generating daily, weekly, monthly and yearly report on the metrics (CPU usage, memory, SLA etc).

Pair it with Grafana and Prometheus.



## Meta Tags

In html, you can get more information from users through click analysis. But just clicking the region would not give much indication on what the user like. So, it's probably interesting to inject metadata to each elements, metadata that contains much more information that is obtained either manually or through machine learning.

https://searchengineland.com/reducing-the-time-it-takes-to-write-meta-descriptions-for-large-websites-299887
https://support.maropost.com/hc/en-us/articles/360015632213-Machine-Learning-for-Recommendations
https://wordlift.io/blog/en/title-tag-seo-using-ai/


## TODO

Trie optimization, and library for the client/server which would allow the data to be more personalized (client-side library) and at the same time up to date with the server's copy (synchronization). Find a way to serialize the data to a more compact format.

## How to ensure that anonymous user does not break certain flows (purchase, registration etc)? 

Create a single unique session that will expire (or can only be used once) and send them a link with that token through email. For each steps, assign a unique bits (1, 2, 4, 8 etc). The email link can only be visited once. If the user complete a step, mark it. If they try to break the steps, forbid them, or ask if they want to restart the flow. The flow can only go in one direction, restarting means repeating the steps from the first one. How to avoid spam (user sending it to another email?). By adding more constraints like the sending can only be done every 5 minutes etc. This url with the token sent is normally called capability url.

## Food for thoughts

- why must the server runs for 24/7? Can't the server just run for a 8hrs a day?
- lifespan of a server, expire after a month
- make the server passwordless

## TODO: Graphql

- handling table joins
- querying with different data sources (mysql)
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
- Data structures and algorithm: https://en.wikipedia.org/wiki/Ford%E2%80%93Fulkerson_algorithm
- find out how to do consistent hashing in different languages (golang, nodejs, python etc)
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
- Document classification
- learn and implement back the software design patterns
- https://en.wikipedia.org/wiki/Software_design_pattern
- https://medium.com/@marinithiago/doing-event-sourcing-without-building-a-spaceship-6dc3e7eac00
- add timeout session for page when user is idle
- Metrics to measure sequence/funnel
- Measure the number of calls for endpoint by user. If a lot of requests is made by a user for login, they might be hacking
- Stateful rest Api design with state machine
- Machine learning anomaly detection refresher
- rate limiting and throttle, they are two different things. Both are enforcing a policy. But we often talk about application level rate limiting (max 10000 requests per second) and consumer rate limiting (5 req per second), but they are actually not the same. The former is daily throttle quota, the latter is rate limit usage.
- Group watch with Netflix idea, share the same subscription but pay in group
- Group forms honestbee
- OWASP Top 10, and how to secure your login form.
- Project setup by just using environment variables. The idea is to have a container that initialises all the basic micro service components such as database and message queue, config loading etc. Then we can just set the environment variables to use those infrastructure. The user may choose to extend the container to add new configuration. The idea is similar to go-kit. Rather than providing user options to fill up, we just define the environment variables that the user have to fill in.

Active service pattern is just a cron job. How to pull data periodically? Return the last update date. MD5 hash the content, or check if the updated date is greater than the previously updated data. If you are pulling a collection, then the greatest last updated date is the indicator.


possible approach
- hide domain from public to debug (not terminate instance or swap image)
- check other services that shares the same db

Getting close. In the next version, come out with several levels of architecture. A good architecture should separate implementation from the abstraction/interface.

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


Music player for the deaf - through vibration/visualization
Digital will for the dead - a message that can only be opened in the future
digital assets - user’s that are popular (reviewer. vlogger, celebrity can have collateral assets, which are their users and also the likes, comments etc). Provide loans to users through with their digital assets as collateral.

Learn about Facebook Pixel and Google Analytics tracker to capture informative data from the website. Do a sample ecommerce testing and see hwat user clicks the most? Check if the solution can be incorporated with A/B testing and also bandit algorithm.


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


How about making a google chrome extension that can execute scripts? Then we can use it to scrape the content and execute the js.


Creation of knowledge base and also kanban board for organization
how to collect useful metrics

Offline architecture
- store images/profile data locally
- Clear it when user logs out
- Logging in with different user should not allow acce



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


## Free programming books

https://github.com/EbookFoundation/free-programming-books/blob/master/free-programming-books.md#ruby

## docker testing gaoling

https://scene-si.org/2019/04/15/next-level-go-testing/

## Vue authentication

https://scotch.io/tutorials/vue-authentication-and-route-handling-using-vue-router

## Sentiment analysis
https://monkeylearn.com/sentiment-analysis/

# Design system

What is essential for a design system?
https://github.com/viljamis/vue-design-system


# using json in sql to replace eav
https://en.m.wikipedia.org/wiki/Entity–attribute–value_model
https://coussej.github.io/2016/01/14/Replacing-EAV-with-JSONB-in-PostgreSQL/

# Dynamic pricing
https://en.m.wikipedia.org/wiki/Dynamic_pricing
https://www.priceintelligently.com/blog/bid/198355/how-to-implement-a-dynamic-pricing-strategy-without-the-pr-backlash
