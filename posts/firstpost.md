---
title: How To Build A Basic Web Component.
description: This is a post on My Blog about getting started with web components.
date: 2022-16-01
tags:
  - webcomponents
  - webdev
  - beginners
  - tutorial
layout: layouts/post.njk
---

Initially, I only knew three things when I started web development: HTML, CSS, and Js. Now there are hundreds of libraries and frameworks to choose from. If you're new to web components, you're at the right place. In this tutorial, I will show you how to build a simple web component using the Lit library.

## First thing first.... What are web components?

A Web Component is a collection of web platform APIs that can be used to create custom, reusable HTML tags that can be used in web pages and web apps. [Learn more](https://developer.mozilla.org/en-US/docs/Web/Web_Components)

Web components are based on existing web standards. The features needed to support web components are currently being implemented to the HTML and DOM specs, allowing developers to extend HTML elements with encapsulated styling and custom behavior.

## Software Installation

Before we get started, you first will need to install some tools.

[Node.js](https://nodejs.org/en/) is an open-source, cross-platform run time environment for executing javascript code. Due to its event-driven, non-blocking I/O model, Node.js is lightweight and efficient, making it ideal for data-intensive real-time applications to run across multiple devices. When you also install Node, you install NPM. NPM is a "package manager" that simplifies and speeds up the installation of Node "packages." A package, also called a module, is just a code library that extends Node by adding useful features.

Once you arrive at the site, you'll want to download the recommended file. To test if node is installed, open up your terminal, type in node on the command line, and hit enter. A welcome text with the latest version of node should appear.

If you get a message saying `zsh: command not found: node` retry downloading Node again. In case you still have trouble installing Node, please refer to this [article](https://nodesource.com/blog/installing-nodejs-tutorial-mac-os-x/).

[Yarn](https://classic.yarnpkg.com/en/docs/install#mac-stable "Yarn installation") is a package manager for your code, enabling you to share and use (e.g. JavaScript) code with other developers. To install Yarn, open up your terminal and type `npm install --global yarn`. Once installed, run `yarn -v`, and the latest yarn version should display.

Once these tools have been installed successfully, we can begin building our first web component.

## Getting Started

1. Start by creating an empty folder and naming it what you like.
2. Inside the directory you just created run `npm init @open-wc`. We will use Open Web Components to get started. You can learn more about it [here](https://open-wc.org/docs/).
3. Next, you'll want to start a new scaffold project. Simply hover over it and press 
`enter` and **select web component**.
4.  Next you'll want to select all available options. You can do this by pressing `a` and hitting `enter`.
5. The next question prompts you if you "would like to use typescript?" We are going to select **no**. The next step is to give our web component a name. **Note:** You need a minimum of two lowercase words separated by dashes—for example, `hello-world`.
6. Next, we will select "yes" for our file structure and install all of our dependencies with **Yarn**. If you weren't successful installing Yarn, you could use **NPM** instead. After a few seconds, all of your dependencies should be installed, and a message saying, "You are all set up now!" would display.

Congratulations!! You have successfully created your first web component. To launch the site, first, you need to make sure you are inside the directory of the web component you just named. You can do this by typing `ls` and then `cd` into the folder. Once inside the directory, you need to run `yarn start` or `npm run start`.

A website would launch every time you start your web component. To terminate the application, press `[control] + c`.

If you have trouble completing the steps above, I recommend watching this [video](https://www.youtube.com/watch?v=r_mio0e6v1g) of my professor walking through the installation process.

##  Next Steps?
Now that you have created your first web component, I recommend you practice and understand the code under the `/src file`.

First, you'll notice the import statement at the top of your javascript file. Here we import the HTML, CSS template literal tags that can be used and rendered with Lit Elements. The Lit element is the base class that manages element properties and attributes.

You might be wondering what the hell is Lit? [Lit](https://lit.dev/docs/) is a simple library for building fast, lightweight web components. With its boilerplate-killing component base class, it offers reactive state, scoped styles, and a declarative template system. You can build just about any type of web interface with Lit.

In the meantime, you can check out Lit's interactive [tutorial](https://lit.dev/tutorial/) on how easy and fast it is to build fast, lightweight web components.

Also, check out [Lit's playground](https://lit.dev/playground/), where you can view and play around with different elements. I recommend you try to resemble the component example; it's simple and an excellent start for beginners. Check out my [repository](https://github.com/reyes-edwin/IST402_Lab-1) and see how I did.

Now that you know how to build your first web component keep exploring! The more you practice, the better you get at it. So happy coding!