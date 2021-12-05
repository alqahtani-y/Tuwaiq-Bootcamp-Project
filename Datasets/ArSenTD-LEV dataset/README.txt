The Arabic Sentiment Twitter Dataset for Levantine dialect (ArSenTD-LEV) contains 4,000 tweets written in Arabic and equally retrieved from Jordan, Lebanon, Palestine and Syria.

The file "ArSenTD-LEV.tsv" is a tab-separated file that contains the corpus and has the following fields:

1. 'Tweet': the text content of the tweet
2. 'Country': the country from which the tweet was collected (one of the Levant countries)
3. 'Topic': the topic being discussed in the tweet (personal, politics, religion, sports, entertainment and others)
4. 'Sentiment' the overall sentiment expressed in the tweet (very_negative, negative, neutral, positive and very_positive)
5. 'Sentiment_Expression': the way how the sentiment was expressed: explicit, implicit, or none (the latter when sentiment is neutral)
6. 'Sentiment_Target': the segment from the tweet to which sentiment is expressed. If sentiment is neutral, this field takes the 'none' value.