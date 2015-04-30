# Re-evaluating Front-end Performance Best Practices
#### Tuesday April 20th 11:15am–11:45am
###### Ben Vinegar  [@bentlegen](http://twitter.com/bentlegen)
[Slides](http://cdn.oreillystatic.com/en/assets/1/event/125/Re-evaluating%20Front-end%20Performance%20Best%20Practices%20Presentation.pdf)

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
Here too there are all kinds of hacks to load dynamicly scripts, (Google's analytics and tag manager also has going overboard with this)

The issue is that they block the CSS rendering (CSSOM + dynamic script insertion) untill the script is excuted, inline scripts can’t execute
until CSSOM ready therfore downloading is delayed.
It also blocks subsequent scripts from downloading.

Another option is to add the `async` attribute to the `script` tag.

### Takeway
don’t always believe what you read on the internet, Experiment yourself, use jsPerf.

#### Notes:
And the best way is to load scripts as the latest posible in the body tag.
Even GA you can break the official loading script apart and try to refactor it so it can be programmatically (dynamicly) be added.
See [understanding-the-google-analytics-tracking-code](http://code.stephenmorley.org/javascript/understanding-the-google-analytics-tracking-code/)  
 
