# Keynotes - Paul Irish
#### Tuesday April 21sh 9am


###How Users Perceive the Speed of The Web
What is slow?  
What metrics do we have?  
- DOMContentLoaded  
- load  
- FPS  
- Jank  
- First paint

We need to rather focus on what "feels slow"
100ms gives the feeling of instantaneous response 
Results feel immediate.
Any longer and the connection between action and reaction is broken.

1000ms  keeps the user's flow of thought seamless. 
Things feel part of a natural and continuous progression of tasks. 
Beyond it, the user loses focus and attention.

Beyond 10 seconds you’ve lost the user's attention.

### Four phases of interaction
- Page load
- Idle
- Response to Input
- Scrolling & Animation

### Rules:
- tap to paint - 100ms
- touch move < 16ms
- scroll < 16
- idle < 50ms (this means we can deliver in the response call
- load < 100ms speed index 1000


### Performance advice abounds
- Don’t use jQuery :hidden
- Don’t use * selectors
- Try/catch forces deopts
- JS animation slower than CSS
- translate3d() for the zoom!
- Event delegation is good
- Event delegation is terrible
- always JSPerf!
- Don’t use with() statement
- Avoid for..in loops
