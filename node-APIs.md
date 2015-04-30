# Re-evaluating Front-end Performance Best Practices
#### Tuesday April 20th 11:15am–11:45am
###### Ben Vinegar  [@bentlegen](http://twitter.com/bentlegen)
[Slides](http://cdn.oreillystatic.com/en/assets/1/event/125/Designing%20a%20Beautiful%20REST+JSON%20API%20Presentation.pdf)

## Lots of the best practices are no longer applicable
There are so many bloggers and developers writing posts and asnwering questions or even code snippets with comments all around the web, a lot of the well known performance practices and hacks are no longer true..    

### hostname sharding
Used to be a patteren that suggested to spread the load of images/resources across multiple servers, but now days many browsers allow 6 to 8 connections, and modren browsers can download multile resources at once. (chrome caps parallel image requests at 10) Also, http/2 will make all this irrelevant.
Take a look at this [Etsy study](bit.ly/rprf-etsy)


### for-loop array length caching
You will find many recomendations to cache variables in a loop, especially the length of the array.

 ```
for(var = i = 0, length = arr.length; i < length; i++){
    // in the loop 
}
 ```

This is no longer needed as modren browser engines optimise these in real time.
Especially v8, only mobile browsers have a very slight diffrence and that is also diminishing..
[Here is how the complied code looks like](http://mrale.ph/blog/2014/12/24/array-length-caching.html), compared the 2 version


### dynamic script insertion 
Here too there are all kinds of hacks to load 
# Methods/types
POST, GET, PUT and DELETE are not a direct 1:1 representation of CRUD
PUT is idempotent so it can’t be partial updates 

POST is used as creation (response 201 + location header of the newly created resource)
It can also be used as update on a instance resource and most importantly it is not idempotent no need for a full representation 
 
In REST you can have different response according to accept header, but they rather should always return the same


# Versioning 
Via URL API/v2/resource
Media type application/&v=2   (how can it be seen in the browser ??)


versions should only rarely be changed for a very good reason

# Dates:
`ISO 8601` is the way to go
MS since EPOC (not best )
UTC

use CreatedAT and updateAt

Should POST return the data return the data too? Yes many reasons mostly for HTTP caching and real server repersantions
You can overwrite by body=false

Header
prioritization on the accept: q paramater 1
The URL is the most important  = .json .csv 

return the href of the API

Linking (xLink in XML) ideas
Directory, groups
Meta

Good ideas for extensive API;s 
Reference expansion = expand=true
Partial pass in fields = as params 



Collections
Pagination 
Size
Pagination (following are he best used names  
first 
next 
previous
Offset  
limit
orderBy (coma delimited list )
Sorting Always have a default 

Search API’s 

Async requests
204 on (accepted)
status: “queued” 
expires on status "sent"


## Batch API
each Batch is a resource
Likely to be a collection 

Batch operations dont  delete the cache



## Errors
as much info as possible (of course mating security secrecy)
Send the status code in the response data 

## Security 

Avoid session based 
Auth based n resource content not on URL
Use API keys instead of username pass’s 
Use Oauth2  
digest set security, HTTPS is not enough 
Guaranty the integrity 
401 vs 403
fusking
etag is like a version for caching to check via if-none-match (304 Not modified)

## Maintaining 

## Testing API’s 
 

## Additional Notes:  
- On my question regarding collections returning as array vs objects for better faster accessing data:  
[async.js](https://github.com/caolan/async)


