# Introduction

This is a series of projects aimed to learn and improve front-end web development. This
was taken from [Tutorial: Intro to React](https://en.reactjs.org/tutorial/tutorial.html) in
the Official React website

To run the project run:
```
$ npm start
```

# What I've learned from building this website

Structuring a project in React seems intuitive, even more than I thought before beginning this tutorial. The basic building blocks that I used throughout this project were:

* React.Component
* React Function Components
* Props and State


I'll go through this in a bit of detail and my observations around them


# React.Component

Checkout the official docs [here](https://en.reactjs.org/docs/react-component.html).

So what I've noticed is that REact lets you define components as classes or functions. Components
defined as classes, in this case one of this basic classes is the "React.Component" interface. The only method required to implement the React.Component interface is the render() method.

```
class Game extends React.Component {

    constructor(props) {
        super(props);
        this.state = {
            // ... attributes for the component ...
        };
    }

    render () {
        return (
            // ... JSX definition of what we want to show on screen ...
        );
    }
}
```

# React Function Components

They are basically defined as normal functions, but take props as an argument. They return a JSX
element that then the parent components can render inside their render() methods. We call them
"function components" because they are literally JavaScript functions:

```
function Square(props) {
    return (
        <button className='square' onClick={() => props.onClick() }>
            { props.value }
        </button>
    );
}
```

# Props and State

Props stands for properties. One very important aspect of them is that they are read-only.
This means that this data is immutable and comes with a number of benefits:
* State is easy to track - we can come back in time with very simple logic.
* Changes are always safe
* Makes all functions "pure" functions.
    - All inputs always return the same output
    - Functions do not attempt to modify their inputs

State basically define the particular state of a React Component. Since React components
that require it need bo te initialized with props, we can then modify the value of this through a
particular state of the React Component. 

```
class Square extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: null,
    };
  }

  render() {
    return (
      <button className="square" onClick={() => this.setState({value: 'X'})}>
        {this.state.value}
      </button>
    );
  }
}
```

As you can see we can modify the initial state defined with "null" using the setState method for 
React.Component.

There are a couple of special methods to the component class that we didn't explore in enough depth:
* componentDidMount()
* componentWillUnmount()

This are called lifecycle methods and hopefully we will cover them in the future.