# Designing a Beautiful REST+JSON API
#### Monday April 20th 11:00am–12:30pm
###### Les Hazlewood (Stormpath)
[Slides](http://cdn.oreillystatic.com/en/assets/1/event/125/Designing%20a%20Beautiful%20REST+JSON%20API%20Presentation.pdf)

# Naming
Api’s that are named verbs are un-scalable  (e.g. getAccountData),  Rather the name of the Instance or collection of instances 
like  

- applications
- applications/{ID}


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


