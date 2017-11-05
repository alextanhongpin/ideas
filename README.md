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
