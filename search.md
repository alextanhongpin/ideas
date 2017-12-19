## Context

Research on how to get the context from the search keyword. Often, the search only performs exact match for keywords, or they will tokenize the search keyword and the context will be gone. Take for example, if you have a search api that will help to search for a job __Product Manager__, it will be tokenized to `product` and `manager` respectively. So if any of the fields you are searching for contains the word `product`, it will return irrelevant results as the scoring will be higher.

## Indexing 

There are several ways of indexing data to Elasticsearch, e.g. is indexing the data daily or by country code. What are the advantages of indexing the data daily for elasticsearch? You can for example search for daily jobs through the index, or a range of indices. By limiting the search, the performance will be better and faster. The downside is that the same documents may be indexed to the different indices and exist for different days when updating the document. Elasticsearch contains a search api to [remove duplicate item](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-terms-aggregation.html?q=terms%20ag). If you index by country, you can optimize the search for countries that uses differnt languages too.

## Multilingual Support

Should be able to support different languages like English, Chinese, Malay, Thai etc.

## Autocomplete

Having a feature to provide autocomplete suggestion is a must if you have a search that is present on the frontend. 

## Autosuggest Recommendations

If the keyword that user search does not return a result (probably due to incorrect keyword), provide relevant suggestions to them.

## Autocorrect

Autocorrect helps avoid typos and improve search accuracy.

## Spam detection

It's rational to have users entering spam keywords. Find a way to prevent that.

