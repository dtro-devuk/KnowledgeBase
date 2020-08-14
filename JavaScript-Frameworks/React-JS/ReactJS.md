# React JS Knowledgbase AUG 2020

Title | Author | Version | Group | Sub-Levels
--- | --- | --- | --- | ---
*React JSX Knowledgebase Page* | dtro-devuk | 1.0 | | **0**


## Intro
React is a JavaScript library to create and compose components.

A front-end library created by Facebook, used for handling the view layer of web and mobile apps.
Enables creation of re-usable components.

*"React is a library for building composable user interfaces. It encourages the creation of reusable UI components, which present data that changes over time. Lots of people use React as the V in MVC. React abstracts away the DOM from you, offering a simpler programming model and better performance. React can also render on the server using Node, and it can power native apps using React Native. React implements one-way reactive data flow, which reduces the boilerplate and is easier to reason about than traditional data binding."*

N.B. React only deals with the UI, View, in MVC.
Its not like Angular, which is now a complete framework.
Angular deals with (UI, Data bindings, Routing, HTTP Calls etc.)
To manage data flows and data (state), Facebook created Flux and Redux.

To create a full SPA in with React, will require use of Flux and Redux, along with other 3rd Party libraries to do routing.

## React Features

* JSX.
* Components (re-use).
* Uni-directional dataflow and Flux (pattern that helps keep data unidirectional).
    * This is also called top-down approach, as the data always flows from the top UI element to the   
  bottom.
* Uses Virtual DOM (a JS Object), faster than regular DOM.
* Needs node js for Development
* The library is easy to learn and use.

2 ways to install React:

1. Using Webpack (bundler) and Babel (transpiler)
2. Using Create React App CLI

Need both React and React DOM
```
npm install react react-dom --save
```

## Why

React is smart at updating the Browser DOM.
You use the React DOM lib to interact with the Browser.

React is a single data-binding framework.

But it does this *smartly* by rendering from the Object tree, when an upadate is needed.

### The React Element Tree

React doesn't use HTML directly. It uses a tree of JavaScript objects to define the UI. 

Each element is created by calling React.createElement() function. 


### SoC

React-dom contains everything needed for browser support. 

The React engine and object tree transformation are separated for a reason. 

React is designed to be open-ended. 

There's also a project called React Native, for example, that renders an object tree with mobile controls to different mobile platforms. 

The object tree is not a UI directly. 
It is an instruction for how the UI should be rendered. 
React hands over this instruction to the DOM library, which will then render it, for the browser. 

*The philosophy of React is that what's displayed in the browser or any other output should be only a **"reflection"** of the state of the application, nothing more.*

This alone is probably a major difference if you compare React with other libraries or frameworks that you might have used before. 

Maybe you have used others that use two-way data binding. React is different. It renders the UI from the object tree every time it needs updating. 

Luckily, it does so in a smart way using something called tree reconciliation.

### Tree Reconciliation

The object tree can change every second, if updates are being made at the server. 

E.g. new data that's being pulled in from the server or user input can cause changes. 

Each time a complete new object tree is created when a change occurs. 

***The magic explained:***

When a new object tree is created, the old one is also kept. 

I.e. whenever a change is made to a portion of the UI, React.js calculates the minimum number of DOM operations needed to achieve the new state. 

This allows page rendering onon every change without worrying about DOM performance.

Todo this:

React has a *smart mechanism* that quickly compares the two trees. 

In a tree of elements, only the element that has changed after the comparison is re-rendered (redrawn).
Then, the old tree, is immediately disposed of.


### JSX
Instead of writing awkward React.createElement syntax You can use a syntax that seems like HTML. 
This is JSX.

Its an extension of React and is syntactic sugar.
Its used with React to describe what the UX should look like.
Its a bit like a template lang, but with the full poYour of JavaScript.

```
    <div>
        <h1>Header</h1>
        <h2>Content</h2>
        <p>This is the content!!!</p>
    </div>
```

This JSX is translated by a tool to the React. createElement syntax. 

Babel can be used to do this translation. Babel is wired into the Create React App CLI, to do this on Build.

Babel is specialized in converting one syntax to another. 

If you go to the Babel Youbsite and paste in some JSX, it translates it to JavaScript. 

* [Babel](https://babeljs.io/en/repl#?browsers=defaults%2C%20not%20ie%2011%2C%20not%20ie_mob%2011&build=&builtIns=false&spec=false&loose=false&code_lz=AQ2g8AmCWBuB8AoMKIAsCM8ASBTAhpLgE7gD0mSqq4aATPAMID2AdgC64fn1XVjgADvAAqaaAGdgk4OzS5gAYzacOAQg3lhyfuRgIgA&debug=false&forceAllTransforms=false&shippedProposals=false&circleciRepo=&evaluate=false&fileSize=false&timeTravel=false&sourceType=module&lineWrap=true&presets=env%2Creact%2Cstage-2%2Cenv&prettier=false&targets=&version=7.11.1&externalPlugins=)

You get:

```
"use strict";

/*#__PURE__*/
React.createElement("div", null, /*#__PURE__*/React.createElement("h1", null, "Header"), /*#__PURE__*/React.createElement("h2", null, "Content"), /*#__PURE__*/React.createElement("p", null, "This is the content!!!"));
```

 NB. There are important differences between JSX and HTML. 
 
 JSX uses *className* instead of class to designate a CSS class.
 
 You also need to keep the following in mind:

#### Uppercase Tag Names

HTML uses lowercase tagnames (reserved), JSX needs have element names start with an Uppercase letter, they should match the JS code for the element.

React DOM components expect DOM property names such as className and htmlFor, respectively.

#### Nested Elements

If you want to return more elements, you need to wrap them with one container element. Notice how a div is being used as a wrapper for h1, h2 and p elements, in the above example.

#### Attributes

You can use our own custom attributes in addition to regular HTML properties and attributes. 
When you want to add custom attribute(s), you need to use a data- prefix. 

e.g.
```
    <div>
        <h1>Header</h1>
        <h2>Content</h2>
        <p data-myattribute = "somevalue">This is the content!!!</p>
    </div>
```

#### JavaScript Expressions
JavaScript expressions can be used inside of JSX. 
You just need to wrap it with curly brackets {}. 

The following example will render 5.

```
    <div>   
        <h1>{2+3}</h1>
    </div>
```

You cannot use ***if else*** statements, but you can use ***conditional (ternary) expressions***

```
    <div>
        <h1>{i == 1 ? 'True!' : 'False'}</h1>
    </div>
```

#### Styling
React recommends using inline styles. 

Setting inline styles, requires camelCase syntax. 
e.g. 

```
var myStyle= {
    fontSize: 100;
    color: green;
}

<div>
    <h2 style={myStyle}>> Title </h2>
</div>
```

React will also automatically append px after the number value on specific elements. 

#### Comments

Need to also be in curly brackets

```
<div>
    {// single line comment}
    {/*
        Multiple line comment
     */}
</div>
```


## Samples
* [React JS Getting Started](https://www.dotnetcurry.com/reactjs/1353/react-js-tutorial)
* [Tutorial Point - React JSX](https://www.tutorialspoint.com/reactjs/reactjs_jsx.htm)


## Resources
* [Intro to React.JS](https://reactjs.org/docs/introducing-jsx.html)
* [Whats React.JS](https://www.reactenlightenment.com/what-is-react.html)

## Courses
* []()
