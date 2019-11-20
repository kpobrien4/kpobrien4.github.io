---
layout: post
title:      "The Asynchronous setState() Function"
date:       2019-11-20 14:36:32 +0000
permalink:  the_asynchronous_setstate_function
---


Within the realm of react, the state of a component manipulates how a specific component acts and is rendered for a user to interact with. State, as opposed to props, can be altered within the respective component containing that state. For example, it can be updated in three ways: event handlers, server responses, and prop changes. React gives us a handy function which provides a means of changing the state of the component, while also rerendering the page in the setState() function. This function asynchronously allows a user to make changes in state that quickly render on the page, rather than setting the state directly where the same thing would not be possible. The function this.setState() takes in an object, containing a literal change to the state which is then merged with the current state. For example, in my latest React/Redux portfolio project, an upvote component was added, which upon clicking a button would change the state of the total upvotes to one more than the current value. To do this I added an event handler that would be triggered on click that looked as follows 

```
      handleClick = (event) => {
        const upvoted = this.state.upvotes + 1
        this.setState({
           upvotes: upvoted 
        })
     }
```

As you can see, using the setState function we are able to make changes to the state which then render on the page immediately each time the event handler is reached. 

The setState function will always rerender the material in question, as long as shouldComponentUpdate() does not return false. Though setState is powerful, it should be used sparingly, to avoid being caught in recursive loops potentially occuring in methods like componentDidUpdate(), which observes whether the new state differs from the previous state. 

Being able to access a function which allows a user to change state and rerender that state is incredibly useful, and can be used in any number of components such as the above mentioned upvote component, but also for a user inputted name, building out a search bar, or changing a boolean from false to true to grant certain privileges to a user. The possibilities are endless!



