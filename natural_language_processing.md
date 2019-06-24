## Identifying user's personality through conversations

How can we understand the user's personality type and tie them to Brigg Myers personality test results?

- from the chat conversation/email content, check the frequency of the most commonly used words
- check the length of the conversation. Length of conversation could indicate certain traits (a closed person, or maybe precise for short conversation, an open person for longer conversation)
- check the response time - how fast they reply to another user. Faster reply time could indicate likeability towards someone.
- check the continuation of the conversation (the number of ping-pongs, which is the messages sent and replied) - how many replies they will take before they stop.
- check the time of the message, does it have a pattern? Is it more frequent in the morning? Is there a repeatable pattern (messaging during lunch time etc)
- check the sentiment of the message
- check the topics of the message. There has to be an intent in every message sent.

## Smart bots with different personality

We can create chat bots with different personality (style) which is trained with different models. One chatbot can be more leaned towards certain kind of responses, or personality.

E.g.
- Chatbot John delivers responses that are short and precise.
- Chatbot Jane delivers longer, more detailed responses.

We can use A/B testing etc. to choose the right chatbot for the right user.

## Relevant Search

Normal search is only matching the keywords/most frequent words etc. Try to incorporate context into search based on the application you are designing. At the same time, try to add personalization to the search.

Most list pages will display a list of items based on typical sorting criteria (by latest, by category, by popularity, by most viewed etc). While it may be a working general solution, it does not add relevancy to users that has searched for something, and want to search for similar things. We could keep a list of what the users has searched before (the recent ones), and add them to the search criteria to compute a more personalized search. It would be great to keep another section to recommend users something related to what they have searched for.

Approach:
- identify intent
- store the search history to build personalized recommendation
- use the previous search term for matching other content/products in other pages

## New Search

Rather than focusing on letting users search on a keyword, provide dynamic recommendations - listing page that changes over time based on the frequency and trend. Users can still search for stuff based on keywords, but this will be the primary feature.


## Named Entity Recognition

Learn and understand the use case of NER. Use NER to understand the context of the word - perhaps optimise it so that it can be used to perform more relevant search and deliver a google-like search experience.

- examples
- how to train your own model
- architecture deployment

Repo [here](https://github.com/alextanhongpin/standford-ner-basic).


## Levenshtein Distance

Understand how to implement dynamic programming with it. There are other several string similarities algorithm that can be used to compute the distance. Find out how this can be used in real world application.

## AutoCorrect

Norvig's autocorrect. http://norvig.com/spell-correct.html


## Create a name generator

Markov chain can be used to generate random names:

http://pcg.wikidot.com/pcg-algorithm:markov-chain

Also, the way docker names are generated is plain simple.

https://github.com/moby/moby/blob/master/pkg/namesgenerator/names-generator.go

https://www.biographyonline.net/people/famous-100.html
https://en.wikipedia.org/wiki/List_of_programmers
https://en.wikipedia.org/wiki/List_of_Pok%C3%A9mon
https://jobmob.co.il/blog/positive-personality-adjectives/

## Applications

- search: Search is an active process - users look for things they want. We can turn them into a passive process through recommendation after learning what users want from their search.
- ranking content: From a list of documents, we can match it against the ones that we desire and rank them. This would allow us to search for content faster, thus saving time. From that, we can also compute similarity for future products.
- spam/filter profanity: This is common in comment/chat system. We search for profanity words and rank the content, blacklisting them when necessary. Paired with user reports/downvotes, this allows us to blacklist poor content from the site.
- mining emails: From the emails we received, cluster them based on topics and find trends.
- trend finding: Scrape twitter/social sites for a topic and find the most common words to draw the trend (most popular language quoted frequently etc). We can use cloud words to display them.
- name generator: we can create a simple name generator. While the application is trivial, this is useful if we have trouble finding ways to name our server etc or stuff that needs dynamic creation with unique labels.
