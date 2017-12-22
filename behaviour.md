# Understanding user behaviour

## Problems

- __Identify__. It is hard to identify which data needs to be logged. There are few approaches to this - the extreme side is to log all the data first without identifying which has more value. The other is progressively identifying which data is relevant, and add them as time goes, but at the risk at losing valuable data if the decision to add new logs takes too much time.
- __Value__. There are many data, but not all are the same - some adds more value than others. For example, the duration the user spend on watching the video they click may be a better indicator on the user's interest rather the action of clicking the video itself.
- __Dependent__. Some data may be dependent to one another, some stands alone. 
- __Time__. Most of the time, concluding the user's behaviour through the historical data is not enough. Since user behaviour change over time, sometimes it is necessary to use the most frequent data to  make predictions. For example, if we have 1000 sets of user's search keyword, it might be more logical to take the last 100 keywords instead of all of them.


## Example

- Click rates tells us about their interest on the item. Get the id of the item they click on and save it as the history. Bandit algorithm can be used to deduce what the user like.
- Duration spent on the application. If we can identify how long they spent on the application, and which page/section, we are most likely to deduce user's interest on that particular page/section/feature.
- Anomaly in behaviour. We can identify user's behaviour if we can trace their behaviour.
- Transition from one feature to another (or after login, or user onboarding). Markov hidden chain can predict the transition. Good to understand if the user is most likely to perform certain action (purchasing, or unsubscribe/churning)
- Targetted marketing/recommendations through user's interest.


## Questions that can be asked

- What is user looking for? 
  - What are the links user click on the page/email? The aggregation of those links will give better indicator on what they are looking for.
  - Identifying the content that user like and how it works on different channels of delivery. Some user's expect certain content (signals to be sent to them)
- Frequency of delivery
  - Users wants real-information. How can we identify which content (e.g. notification of approval of loan) to be delivered real-time, versus others that can be sent at later times.
- Why do user unsubscribe?
  - How many days pass by before user unsubscribe from an email? Are we spamming to much?
- How active is the user?
  - What is the duration user spend on desktop web vs mobile web? If we know which platform they use more, we can work on developing better experience on the specific platform.
  - What is the last activity on the mobile, web, ios/android etc. If we know this, we can send the relevant push notifications to user by predicting the time they will be active on each platform.
- What is the action that user's performed the most?
  - If we can identify the user's transition, we can probably identify what can steps to be reduced. Example, if the user spends a lot of time at the search page, and retrying multiple filters to get the result they want, it's probably an indicator that the search is not optimized, and there are many steps that needs to be taken to get relevant results. Perhaps optimize the search of find ways to reduce the steps for the search.
  


## Category of users

We can categorize user's by the following behaviour:

- Fake. Create fake accounts for the sake of the toying with others.
- Active/Inactive. Classification by duration spent.
- Happy/Angry. Classfication by feelings.
- Participating/Observer. Classification by activity - some users are active all the time, but they are not necessarily participating (buying stuff, applying for loan).

## Type of contents/feature.

- Display only. Contents that are readable. Good indicator of what interest the users.
- Engaging. Users can interact with them (search, call-to-action)
- Requires completion. Example form for purchasing items.
