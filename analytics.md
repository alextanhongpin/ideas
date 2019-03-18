# Analytics

It's good to have dashboard to visualize the output. But rather than visualize, it's better to `verbalize` the output. Let's say we have a goal to increase the CTR, from the data your acquired, you can put them in words:

- We accomplished 20% improvement in CTR over the last `day/week/month/year`.
- We have higher click rates on `mobile` than `desktop`.


## Capturing signals from user.

For example, if you want to know if the user is interested in the price, don’t make is visible. Make user click on the show price to view the price. This is a signal that can be captured.

## Stale data

Understand that data that are logged can be stale if they are not used. Knowing what to do with the data is more important than logging them.

## Data that can be captured

- timestamp
- event name
- caller id
- ip
- region
- latitude/longitude (last ten values, since user moves from one place to another)
- last city
- last login
- last device
- device type (ios, android)
- device name
- screen size
- platform (web, mobile web, mobile native) and also transition between platfroms (night ipad, morning iphone, evening web etc)
- search keywords
- last 10 search (take the last ten instead of historical all value because user preference changes over time)
- pages visited
- links clicked
- duration online
- frequency online
- minute/hour/day/week/month/year online
- current geographical events/celebrations
- referer url
- sequence of actions performed
- what features perform best on what devices
- what is the value of the features (determined by clicks, duration used, lifespan etc)
- click rates

## Metrics Domain

Capturing data can be done for separate domains. Domains differs by context, such as monitoring, analytics, deployment and also time-series. 

- **monitoring** is used to capture the application performance, e.g. CPU Usage, requests count, errors. See the [USE Method](http://www.brendangregg.com/usemethod.html) by Brendan Gregg.
- **analytics** covers more on the application logic - how the user's are using our application, their journey etc. Also the latency they experience. OpenTracing is a good tool to capture this metrics, as we can apply the Hidden Markov Model to carry out churn prediction for example.
- **deployment** captures metrics on deployment and the duration. Allow us to see how frequent is the deployment, and how we reach from planning to release. Also, it's important to compare the metrics captured between different version (V1 vs V2 releases) to see if there are improvements.
- **test coverage** describes the reliability of a system, on how it is supposed to perform

## Monitoring Services

Monitoring services is more than logging the latency, request count, request rate, errors etc. The erros count can be part of monitoring, and also reporting SLA (Service Level Agreement).

Latency and requests rate provides information on the improvement we made on a service (from V1 to V2), and enables us to trace the outcome of the deployment (similar to benchmarking in test, but this is carried out in production. Of course, benchmark it in test first, the production data is just a support for the improvements conducted).


## Accuracy

Dealing with metrics (e.g. counter) can be tricky - if we have retry pattern that will retry a request, it will increment the counter for both errors and requests. The data captured will be inaccurate, and hence require better way of capturing. For better precision, it would be better to log both the service requests together with a unique id and timestamp so that we can eliminate duplicate call.

## Implement Web Beacon for Frontend to gather analytics data

https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon


## Proving Pareto's principle

- check if 20% of the customer generates 80% of the revenue

## Frequent Pattern

Data mining 

## Analytics 

Having data is useless if we only use them to plot charts - it has to generate _actionable actions_. For example, can we find out if:

- what product generates the most revenue?
- how does the trend changes over year
- who are the top 20% product that generates the most revenue?
- who are the top 20% users that purchase the most? are they recurring purchases of the same product? what can we do to engage those users so that they continue buying/staying loyal?


## Emails

- get more email views by adding `Re: subject` in front of the subject.
- how to send personalized email to all users? The answer is - you can't. If you are sending the emails to all users, it is gonna be generic. The best way is to take 20% of the top purchasers (based on Pareto's principle), observe their buying habits, deduce their personality and send them a personal email. 20% of 100k is too many? Then start by sending 100 emails first. Some things have to be done manually, and then once we have found the sweet spot for the (effort to results ratio), automate it.

## Driving data decision

- if we are plainly looking for analytics, we can strip of customers information (email, id, names etc), since we do not need to use them to derive value
- if we are looking for recommendations, we need to at least match their preferences with the behaviours
- most basic metrics includes daily, weekly, monthly or yearly sales (trends etc)

