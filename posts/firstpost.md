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

A Web Component is a collection of web platform APIs that can be used to create custom, reusable HTML tags that can be used in web pages and web apps. [Learn more](https://dev.to/reyesedwin/how-to-build-a-basic-web-component-mjo#:~:text=and%20web%20apps.-,Learn%20more,-GIF)

Web components are based on existing web standards. The features needed to support web components are currently being implemented to the HTML and DOM specs, allowing developers to extend HTML elements with encapsulated styling and custom behavior.

## Software Installation
Before we get started, you first will need to install some tools.

[Node.js](https://nodejs.org/en/) is an open-source, cross-platform run time environment for executing javascript code. Due to its event-driven, non-blocking I/O model, Node.js is lightweight and efficient, making it ideal for data-intensive real-time applications to run across multiple devices. When you also install Node, you install NPM. NPM is a "package manager" that simplifies and speeds up the installation of Node "packages." A package, also called a module, is just a code library that extends Node by adding useful features.

Once you arrive at the site, you'll want to download the recommended file. To test if node is installed, open up your terminal, type in node on the command line, and hit enter. A welcome text with the latest version of node should appear.

If you get a message saying `zsh: command not found: node` retry downloading Node again. In case you still have trouble installing Node, please refer to this article.

[Yarn](https://classic.yarnpkg.com/en/docs/install#mac-stable "Yarn installation") is a package manager for your code, enabling you to share and use (e.g. JavaScript) code with other developers. To install Yarn, open up your terminal and type `npm install --global yarn`. Once installed, run `yarn -v`, and the latest yarn version should display.

Once these tools have been installed successfully, we can begin building our first web component.

## Getting Started

1. Start by creating an empty folder and naming it what you like.
2. Inside the directory you just created run `npm init @open-wc`. We will use Open Web Components to get started. You can learn more about it [here](https://open-wc.org/docs/). If successful, you should get the same results as me.



