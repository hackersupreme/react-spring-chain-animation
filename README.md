# React Spring Chained UI Animation

Contents
- Overview
- Live Site
- Installation
- Code Sandbox Documentation
- Github Documentation
- Resources / Contact Info

## Overview

React-Spring is a spring based animation library. Since the animations are spring based and not duration based, UI elements move more naturally.

An example of this is the UI component in [this](https://codesandbox.io/embed/2v716k56pr) demo code sandbox from the official documentation. It moves fluidly and is a good way to convey grid-like content.

In this document I'll provide documentation for how that code sandbox demo works and provide an example of it I make on my own. I'll provide documentation for my creation as well. 

Note: the files in this github are from my example.

[Here](https://www.react-spring.io/docs/hooks/use-chain) is the page of the official React-Spring docs where this demo is shown.


The demo is a good UI component to know how to use. It provides white space emphasizing a title or call to action and smoothly transitions the user to some content related to that.

I wanted to imagine what I could do with this component in the context of a blog. This is what I came up with.



If you want to avoid clutter on your page but also want to include a grid of content like blog posts you can use this component to accomplish that.

## Live Site

http://react-spring.hackersupreme.com/hooks/chain

## Installation

These steps assume you have [Gatsby.js](https://www.gatsbyjs.org/) and [Node.js](https://nodejs.org/en/) installed on your computer.

1. Create local directory for the project to live in
2. Download the files into that directory
3. Use a [cli](https://www.w3schools.com/whatis/whatis_cli.asp) and navigate into that directory
4. Use `npm install` to download the necessary node modules
5. Use `gatsby develop` to launch the server

## Code Sandbox Documentation

The hook used to accomplish this animation is the `useChain` hook. This hook allows you to chain multiple different animations in a row.

This demo chains together a `useSpring` hook and a `useTransition` hook. In order for a chain to work, each animation must have a ref passed along to it to block it from starting on its own.

If the hook `useRef` is unfamiliar to you, check out the [documentation](https://reactjs.org/docs/hooks-reference.html#useref) on React.js's site.

A `useSpring` hook simply animates a value. The `useSpring` hook in this chain fires first and animates the container element to change color from pink to white and the size of the container element to go from 20% to 100%.

_From the demo_
```
  const springRef = useRef()
  const { size, opacity, ...rest } = useSpring({
    ref: springRef,
    config: config.stiff,
    from: { size: '20%', background: 'hotpink' },
    to: { size: open ? '100%' : '20%', background: open ? 'white' : 'hotpink' }
  })
```


## Resources / Contact Info

