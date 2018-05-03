# CustomerAPI
assignment

Use Case 1
1.	A consumer may periodically (every 5 minutes) consume the API to enable it (the consumer) to maintain a copy of the provider API's customers (the API represents the system of record)

If a consumer is consuming the API in every 5 minutes then there should be certain fields in response body or response headers which tell about  the modified time of the costomers data  and headers like count will tell about the any new customer data addition.
We can also make use of the response header Etag in case of caching at server side for mobile apps which allows the consumer to understand if the certain response has been updated since the last call or not.


Use Case 2 

2.	A mobile application used by customer service representatives that uses the API to retrieve and update the customers details.

For a mobile customer all the calls should happen using HTTPS so our RAML should allow the API Calls to come using HTTPS protocol.
Since for mobile client, responses from server side  needs to be light weighted due to which  heavy data needs to be kept at server side
So caching can be done at server side and modified last and Etag Headers  can be used to send in responses to update  mobile client  if the data has been last modified since last updated. and if data has not been updated then a simple 304 not modified status code can be sent .
Also pagination can be used in request headers to filter the data and then send the light weighted data page by page as requested by client or mobile app.


Use Case 3

3.	Simple extension of the API to support future resources such as orders and products

We can have empty resources in RAML file to support future resources and everytime a request coemes to these resource  "401 resource not available" can be sent in response whenever client tries to hit these resources.
