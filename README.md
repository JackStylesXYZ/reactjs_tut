# React JS

### What is React?

React is an open source library founded by [Meta](https://meta.com) (*formally [Facebook](https://facebook.com)*) and they state that React is... 
> React
>
> *" A JavaScript library for building user interfaces "*
>
> -- <cite>[reactjs.org](https://reactjs.org)</cite>

Some of the main concepts and phrases used to describe React are...
* Declaritive
* Component-based
* Learn Once, Write Anywhere


So we've heard a few concepts and phrases that might be new to us, so let's dive in and unravel them...

---
### User Interface (UI)

According to wikipedia a user interface is...

> *In the industrial design field of human–computer interaction, a user interface (UI) is the space where interactions between humans and machines occur.*
>
> -- <cite>[en.wikipedia.org](https://en.wikipedia.org/wiki/User_interface)</cite>

Out of the box React gives us a library of *"things"* that will help us build user interfaces for our wep applications. If you're familuar 

React can help us compose complex User Interfaces from samll and isolated pieces of code called *"[Components](https://reactjs.org/docs/react-component.html)"*



---

# Working Examples

### Javascript

In this example we will be using javascript to create a new div and append that as a child to an existing div within the DOM.

For the code please look at the folder `Examples/1_Javascript`

We have a simple html document containing a single div within the body tag - this div has the id of ***"root"***, and a script tag following the body tag containing our javascript code for this example.

### pseudo code...
```
1 - grab the div with the id of "root"
2 - create a new div element
3 - add some text the the new div - "Hello, world!"
4 - add a classname to the new div
5 - append the new div to the div with id of "root"
```

### Javascript code...
```
  1 - const rootElement = document.getElementById('root')
  2 - const element = document.createElement('div')
  3 - element.textContent = 'Hello, world!'
  4 - element.className = 'data-javascript-only'
  5 - rootElement.appendChild(element)
```