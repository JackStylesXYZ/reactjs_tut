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

### Javascript Only

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

---

## React.createElement()

In this example we'll use React and React DOM to manipulate the DOM to achieve the same output as example Examples/1_Javascript. We'll have to include a couple of script tags within the head of our index.html file using a CDN -  this will expose the React object and ReactDOM object for us to use in our code.

For the code please look at the folder `Examples/2_ReactCreateElement`

### pseudo code...
```
1 - grab the div with the id of "root"
2 - create a new div element
3 - add some text the the new div - "Hello, world!"
4 - add a classname to the new div
5 - append the new div to the div with id of "root"
```

### React.createElement() code...
```
  1 - const rootElement = document.getElementById('root');
  2, 3, 4 - const element = React.createElement("div", {className:'data-example'}, "Hello, world!");
  5 - ReactDOM.render(element, rootElement);
```

As you can see from our updated code (now using React.createElement()) there are a few differences.
React is now taking care of all the DOM manipulation for us, we are still grabbing the "root" element in the same way as example 1 BUT then we are using React in steps 2-5.
When we call [React.createElement()](https://reactjs.org/docs/react-api.html#createelement) it expects a few arguments:  
-  type
-  props
-  children

The *type* in our example is a "div"
The *props* in our example is an object with the className
The *Children* in our example is simply the text "Hello, world!" - BUT we could add another call to React.createElement() if we wanted to nest another new element within our "root" div, lets take a look below:  

```
  <script>
    const rootElement = document.getElementById('root');
    const element = React.createElement('div', {className: 'data-example'}, React.createElement('div', {className:'data-level-two'}, React.createElement('h1', {className:'data-level-three'}, 'Title H1 Text')));
    ReactDOM.render(element, rootElement);
  </script>
```

In the example above I have nested another "div" with a nested "h1" inside of that, so we now have div#root -> div.data-example -> div.data-level-two -> h1.data-level-three

As you can see when we start to nest, or deeply nest React.createElement() calls one within another it soon becomes a little overwhelming and complicated to read / understand, this is where React + JSX comes into help.

