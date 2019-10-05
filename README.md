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


## Fraud Detection



Compare content between different files. Say we have a claims and we uploaded the file. And we have a user with the name, gender etc. We can check if the information in the file still matches, last date etc etc.

Fraud detection:

https://www.altexsoft.com/whitepapers/fraud-detection-how-machine-learning-systems-help-reveal-scams-in-fintech-healthcare-and-ecommerce/

https://www.datascience.com/blog/python-anomaly-detection
https://www3.cs.stonybrook.edu/~leman/icdm12/ICDM12-Tutorial%20-%20PartI.pdf
https://towardsdatascience.com/how-to-use-machine-learning-for-anomaly-detection-and-condition-monitoring-6742f82900d7
https://towardsdatascience.com/5-ways-to-detect-outliers-that-every-data-scientist-should-know-python-code-70a54335a623
https://en.m.wikipedia.org/wiki/Anomaly_detection
https://medium.com/m/global-identity?redirectUrl=https%3A%2F%2Fblog.statsbot.co%2Ftime-series-anomaly-detection-algorithms-1cef5519aef2
https://medium.com/analytics-vidhya/anomaly-detection-strategies-for-iot-sensors-6281e84263df
https://medium.com/@mehulved1503/outlier-detection-and-anomaly-detection-with-machine-learning-caa96b34b7f6
https://www.kdnuggets.com/2018/12/four-techniques-outlier-detection.html
https://towardsdatascience.com/wondering-how-to-build-an-anomaly-detection-model-87d28e50309
https://github.com/shubhomoydas/ad_examples
https://www.ritchieng.com/machine-learning-anomaly-detection/
https://blog.floydhub.com/introduction-to-anomaly-detection-in-python/


Distance similarity

https://towardsdatascience.com/3-basic-distance-measurement-in-text-mining-5852becff1d7
https://medium.com/@adriensieg/text-similarities-da019229c894
http://aircconline.com/mlaij/V3N1/3116mlaij03.pdf


Data streams preprocessing
https://medium.com/high-alpha/data-stream-processing-for-newbies-with-kafka-ksql-and-postgres-c30309cfaaf8
https://www.infoq.com/articles/data-processing-redis-spark-streaming/


Is there a way of returning partial scoring (think streaming). Say, for fraud detection, we usually want to find if a transaction is a fraud, but it may take day etc. Can we return the confidence score partially, and request data at the same time to improve the final score? We can use this in job applications too. Say, every step that the employer performed will be notified to the user, from receiving the application, initial screening, feedbacks etc will be delivered step by step to the end user.


String similarity
- edit distance based. Computes the number of operations needed to transform one string to another. More operations means less similarity. 
- Token based. Instead of string, the expected input is a set of takens. The more the number of tokens, the more similar the sets are. 
- Sequence based. Finding the common substrings between two strings. The longer the longest sequence, the higher the similarity score. 

1. edit distance based
hamming distance
levenshtein distance
damerau-levenshtein distance
jaro winkler distance

2. Token based
jaccard index
jaro-winkler distance
sorensen dice

3. Sequence based 
ratcliff-obershelp similarity (gestalt pattern matching)


https://asecuritysite.com/forensics/simstring

 
string search (boyer moore grep algorithm)


Hypothesis: User likes the color blue

How to measure execution time of user to complete an action?
Simple, when the component starts, set the start time. When the user completed the action such as submitting a form, record the time taken.
Catfooding. Use a competitor app and try out their functions. What did they do well, what they did not do well?
Dogfooding. Use our own app. List back our top features (should be measurable), and give a list of tasks. See how long it takes to complete them.


Recording time. Users can just enter and exit the feature. We do not want to record that (sampling). We only sample if the user stays on the screen more than X seconds, or has initiated the first step.


## Brig Myers

brigg myers personality test

* Basic data cleaning (or the lack thereof - its actually quite clean already)
* Extract weblinks from each user, and
    * Further divide the weblinks into video, images and others
    * For videos, extract video titles from the respective sites (not used)
    * For images, extract keywords (not done)
    * For other websites, obtain categories (not done)
* Split the target data from 16 categories into 4 binary classifiers (The why will be explained below)
* Extract other metadata:
    * Emoticons (eg. :happy:)
    * Mentions (eg. @tamagonii)
    * Hashtags (eg. #ilovetamago)
    * MBTI reference (eg. INFP, ENFJ) (not used)
    * Action words (eg. *jumps into the pool and swim away*)
    * Enneagram regerence (eg. 4w1) (not used)
    * Brackets (eg. [quote])
    * Dots count (…)
    * Number of words
    * Number of word characters
    * Number of fully capitalized words (eg. HEY Y’ALL!!)
    * Number of characters of fully capitalized words
    * Ratio of fully capitalized words vs all words
    * Ratio of characters of fully capitalized words vs characters of all words
    * Median number of words used per person
    * Median number of characters used per person
* Perform Parts-of-speech (POS) tagging to the word document
* For each MBTI type,
    * Perform Term Frequency - Inverse Document Frequency (TF-IDF)
        * For word range of 1-3, up to 10,000 words/phrases each
        * For each word, apply Truncated Singular Value Decomposition (Truncated SVD) to reduce the size to 500 features each, totalling 1500 features
    * Pre-process the data:
        * Perform Standard Scaling on metadata
        * Combine with TFIDF data, and perform MinMax Scaling
    * Select 100 best features using chi2 test
    * Train the model with Logistic Regression
* Collect instances of all 4 types to predict data from new input data
* Done!

## Decision
Make purchase decision easier
- create reusable profiles for recurring purchases. User can switch the profile for family, self, etc
- Is it a one time purchase? Make the forms easier to purchase.
- How to convince user that the right decision is being made? Once the user select the item, throw the anchor 80% of the user buy this too (this statistic is based on the what the customers purchase the most in general, we do not include the actual number, just the percentage. Also, we do not show it in the listing page to reduce bias on what products to buy. We just want to trigger the user to make the final decision.
- Instead of showing a listing, do a listing with a recommendation. E.g. how about purchasing xyz. This gives user an option straight away if they do not know what the are looking for.


Create a lead tracker that allows scraping potential leads. Also, use google url tracker to see how is the progress. When providing url to the leads, customise the websites content to fit what the leads are interested in.


Define Decision
Recommend the user … 
Start Date:
End Date:
Difference measured during this period:
Does it work well?
Notes



How about making a google chrome extension that can execute scripts? Then we can use it to scrape the content and execute the js.


Unit test for sequential actions
- assert, act arrange
- Should the unit test be allowed to test sequential operations? This is more leaned towards behaviour driven development


topic modelling


what is topic modellling?
a branch of unsupervised natural language processing which is used to represent a text document with the help of several topics.

Why do we need topic modelling.
- grouping words in such a way that each group represents a topic in a document. E.g. finding similar questions on StackOverflow, news flow aggregation and analysis, recommender system.
- topic models helps us make recommendations about what to read next by finding materials that have a topic list in common
- improve search result by revealing documents that may use a mix of different words but are about the same idea

Latent Diriclet Allocation
- Latent: This refers to everything that we don’t know apriori and are hidden in the data. 
- Dirichlet: Distribution of distributions. In the context of topic modelling, dirichlet is the distributions of topics in documents and distributions of words in the topics.
- allocation: Once we have the dirichlet, we will allocate topics to the documents and words of the documents to topics.

https://medium.com/@tomar.ankur287/topic-modeling-using-lda-and-gibbs-sampling-explained-49d49b3d1045

https://towardsdatascience.com/topic-modeling-and-latent-dirichlet-allocation-in-python-9bf156893c24

https://medium.com/@lettier/how-does-lda-work-ill-explain-using-emoji-108abf40fa7d
https://towardsdatascience.com/nlp-extracting-the-main-topics-from-your-dataset-using-lda-in-minutes-21486f5aa925


Genetic Algorithm

https://blog.floydhub.com/introduction-to-genetic-algorithms/?fbclid=IwAR3w-xWcDpoLSFn35UrDu2sybIhbDUHqojyiig51j7Kvc2z4vFOxCXhf6SA


Creation of knowledge base and also kanban board for organization
how to collect useful metrics

Offline architecture
- store images/profile data locally
- Clear it when user logs out
- Logging in with different user should not allow acce

thought/questions

- do I need a degree/masters/phd in order to do data science? no, just focus on what you are doing.

courses (find the itinerary for data science / big data courses, and you will know the direction
- data preprocessing
- regression: simple linear regression, multiple linear regression, polynomial regression, SVR, decision tree regression, random forest regression
- classification: logistic regression, knn, svm, kernel svm, naive bayes, decision tree classification, random forest classification
- clustering: k means, hierarchical clustering
- association rule learning: apriori, eclat, fp-growth
- reinforcement learning: upper confidence bound, thompson sampling
- natural language processing: bag of words and algorithms for NLP
- deep learning: artificial neural networks, convolutional neural networks
- dimensionality reduction: PCA, LDA, kernel PCA
- model selection and boosting: k-fold cross validation, parameter turning, grid search, XGBoost.
- ss to the data
- 



How to predict gender from name
From profile photo
From conversation style
From email 

https://www.learnopencv.com/image-alignment-ecc-in-opencv-c-python/
https://www.learnopencv.com/image-alignment-feature-based-using-opencv-c-python/


Use open street map
https://nominatim.org/release-docs/develop/api/Reverse/

https://wireframe.cc/ifjJP6


## Analytics

To avoid tracking on testing/development environment, filter the url localhost

https://developers.google.com/analytics/devguides/collection/analyticsjs/
https://segment.com/docs/guides/best-practices/how-do-i-collect-pageviews-on-the-server-side/

# Big Data

How counting is done with big data

https://towardsdatascience.com/big-data-with-sketchy-structures-part-1-the-count-min-sketch-b73fb3a33e2a
https://towardsdatascience.com/big-data-with-sketchy-structures-part-2-hyperloglog-and-bloom-filters-73b1c4a2e6ad


## Big Data Design Patterns

https://hub.packtpub.com/common-big-data-design-patterns/
https://www.innoarchitech.com/blog/scalable-software-big-data-analytics-architecture-architectural-design-patterns
https://azure.microsoft.com/en-in/blog/the-emerging-big-data-architectural-pattern/
https://www.datasciencecentral.com/profiles/blogs/11-core-big-data-workload-design-patterns

# Machine Learning

Statistical data distribution
https://machinelearningmastery.com/statistical-data-distributions/

Probabilitistic distribution
- why are they important?
- how can we use it in our application?

https://bigdata-madesimple.com/how-to-implement-these-5-powerful-probability-distributions-in-python/


## How to apply neural network to your web application?

- what kind of data is required?
- what kind of input/output is expected?
- how to deploy a simple machine learning pipeline using Flask?
- how to use tensorflow.js on the client side

https://towardsdatascience.com/neural-networks-to-predict-the-market-c4861b649371
https://hackernoon.com/build-your-first-neural-network-to-predict-house-prices-with-keras-3fb0839680f4
https://www.solver.com/neural-network-prediction
https://www.obitko.com/tutorials/neural-network-prediction/
https://medium.com/datadriveninvestor/making-your-first-neural-network-part-3-988dc271af0
https://medium.com/@robertjohn_15390/simple-housing-price-prediction-using-neural-networks-with-tensorflow-8b486d3db3ca
https://blog.statsbot.co/neural-networks-for-beginners-d99f2235efca
https://hackernoon.com/how-to-build-and-use-neural-networks-c2a0de2e07d9
https://www.quora.com/What-are-the-applications-of-neural-networks



## Recommendation engine


With surprise:
using a library instead of implementing one yourself
https://realpython.com/build-recommendation-engine-collaborative-filtering/

Learning to rank with Bayesian Personallzed Ranking from implicit feedback
https://researchcode.com/code/1395261448/bpr-bayesian-personalized-ranking-from-implicit-feedback/
https://medium.com/radon-dev/als-implicit-collaborative-filtering-5ed653ba39fe
https://towardsdatascience.com/recommender-system-using-bayesian-personalized-ranking-d30e98bba0b9

Recommendation with Singular Value Decomposition (SVD)

- how to build the svd matrix?
- how to perform dimensionality reduction?
- how to add new users?
- how to update the ranking when new items are added

http://rstudio-pubs-static.s3.amazonaws.com/335300_11d40bf12d8940f78d9661b3c63150dc.html
http://www.cs.carleton.edu/cs_comps/0607/recommend/recommender/svd.html

Using machine learning to rank
https://dec0de.me/2014/10/learning-to-rank-1
https://towardsdatascience.com/learning-to-rank-with-python-scikit-learn-327a5cfd81f
https://thenewstack.io/letor-machine-learning-web-search-technique-thats-turned-key-information-retrieval-tool/
http://times.cs.uiuc.edu/course/598f14/l2r.pdf


## Elasticsearch


How to implement search for web applications?

https://github.com/CatalystCode/CustomSearch
https://github.com/linkedin/instantsearch-tutorial/blob/master/data/stackoverflow/posts_10K.json


##Rust

How to implement basic services?
- that includes middleware
- asynchronous db calls?
- async/await
- clean code architecture

https://danielwelch.github.io/rust-web-service.html
https://zupzup.org/rust-webapp/
https://gill.net.in/posts/auth-microservice-rust-actix-web1.0-diesel-complete-tutorial/

Rust functional programming jargon

https://functional.works-hub.com/learn/functional-programming-jargon-in-rust-1b555

## Testing

https://github.com/goldbergyoni/javascript-testing-best-practices

## Time to group the learnings
- by languages
- by tools
- by domains
- by problems
- by usecases
