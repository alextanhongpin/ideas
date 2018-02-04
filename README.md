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


## Genetic Algorithm

Write your own implementation of Genetic Algorithm and look into the application in web/mobile.

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
