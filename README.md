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
