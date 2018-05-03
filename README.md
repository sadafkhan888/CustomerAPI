# CustomerAPI
assignment
Use Case 1
1.	A consumer may periodically (every 5 minutes) consume the API to enable it (the consumer) to maintain a copy of the provider API's customers (the API represents the system of record)

If a consumer is consuming the API in every 5 minutes then shpu;d be certain fields in response body or response headers which tell about  the modified time of the consumer and any new addition.
We can also make use of the response header Etag which allows the consumer to understand if the certain response has been updated since the last call or not.

Use Case 2 
2.	A mobile application used by customer service representatives that uses the API to retrieve and update the customers details.
For a mobile customer all the calls should happen using HTTPS as it will mobile calls will be on secure network also
Since mobile client needs to be light weighted and so heavy data needs to be kept at server side
So caching can be done at server side and modified last and Etag can be used to update mobile client to know if the data has been last updated or not. Also pagination can be used in request headers to filter the data and then send the light weighted data page by page as requested .


Use Case 3
3.	Simple extension of the API to support future resources such as orders and products
We can have empty resources created in RAML file to support future resources and a simple 401 resource not available can be sent in response whenever client tries to hit these resources.
