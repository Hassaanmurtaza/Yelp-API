# Yelp-API
API to import businesses data from yelp using requests api

In this API I have used requests.get() to query the Yelp Business Search API for cafes in New York City. requests.get() needs a URL to get data from. 
The Yelp API also needs search parameters and authorization headers passed to the params and headers keyword arguments, respectively.

I extracted the data from the response with its json() method, and passed it to pandas's DataFrame() function to make a dataframe. 
The necessary data is under the dictionary key "businesses".

Formatting parameters to get the data you need is an integral part of working with APIs. 
These parameters can be passed to the get() function's params keyword argument as a dictionary.

The Yelp API requires the location parameter be set. It also lets users supply a term to search for. 
I used these parameters to get data about cafes in NYC, then process the result to create a dataframe.

Many APIs require users provide an API key, obtained by registering for the service. Keys typically are passed in the request header, rather than as parameters.

The Yelp API documentation says "To authenticate API calls with the API Key, set the Authorization HTTP header value as Bearer API_KEY."

The Json data fetched from the API was nested: meaning that the attribute value can consists of other atribute value pairs
So I flattended the data using the json_normalize method

The categories attribute in the Yelp API response contains lists of objects. 
To flatten this data, I employed json_normalize() arguments to specify the path to categories and pick other attributes to include in the dataframe.
