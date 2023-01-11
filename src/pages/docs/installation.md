---
title: Installation
description: Quidem magni aut exercitationem maxime rerum eos.
---

The steps to installing vue is very simple. 

---

## Install Nodejs

Node.js is a cross-platform, open-source server environment that can run on Windows, Linux, Unix, macOS, and more. Node.js is a back-end JavaScript runtime environment, runs on the V8 JavaScript Engine, and executes JavaScript code outside a web browser.

[Nodejs](https://nodejs.org/) 

### Create Vue apps

There are a number of way to install vuejs on your machine. 

```shell
npm init vue@latest
or
npm create vue@3
```


### Install Dependencies

 A dependency is additional code that a programmer wants to call. Adding a dependency avoids repeating work already done: designing, writing, testing, debugging, and maintaining a specific unit of code.

The next step is to install all needed dependencies for your project. Unfortunately it is hard to figure out all dependencies required before the start a project. You can install the rest as and when you need them

Run this code to install a package

```shell
npm install <package name>
or 
npm i <package name>
```

---

## Tailwindcss

Tailwind CSS works by scanning all of your HTML files, JavaScript components, and any other templates for class names, generating the corresponding styles and then writing them to a static CSS file.

Follow the link to install and configure [Tailwindcss](https://tailwindcss.com/docs/guides/vite) 

### Configure tailwindcss.config.js
Add .vue extension so tailwind work on vue files
```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx,vue}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
