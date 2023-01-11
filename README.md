# Setup React TDD development environment 
Setup React development environment without Create React App.
This tutorial will guide you to setup and install React development environment using these technologies:

- React
- Babel
- Webpack
- Jest
## 1. Set up a new npm package
```cmd
npm init
```
![img-01]

This will create a new npm package and a new package.json file.

## 2. Install React
```cmd
npm install --save react react-dom
```
This will install ReactJS and it dom packages.

![img-02]

## 3. Install Jest
```cmd
npm install --save-dev jest jest-environment-jsdom
```
This will install Jest testing library.

![img-03]

## 4. Install Babel, the javascript compiler
```cmd
npm install --save-dev @babel/preset-env @babel/preset-react @babel/plugin-transform-runtime @babel/core babel-loader
```

![img-04]

## 5. Install webpack, a static module bundler
```cmd
npm install --save webpack webpack-dev-server webpack-cli
```
```cmd
npm install --save-dev html-webpack-plugin
```

![img-05]
![img-06]

## 6. Install Tailwind CSS, as a PostCSS plugin
```cmd
npm install --save-dev tailwindcss postcss autoprefixer
```
![img-07]


## 7. Install CSS loaders
```cmd
npm install --save-dev style-loader css-loader postcss-loader
```
![img-08]

## 8. Config Babel
Create a file .babelrc
```cmd
touch .babelrc
```
and with these content
```javascript
{
  "presets": ["@babel/env", "@babel/react"],
  "plugins": ["@babel/transform-runtime"]
}
```
![img-09]

## 9. Edit package.json for Jest config
Add the following to package.json
```javascript
"jest": {
  "testEnvironment": "jsdom",
  "globals": {
    "IS_REACT_ACT_ENVIRONMENT": true
  }
}
```
![img-10]

## 10. Edit package.json for commands
Add the following to package.json for npm command
```javascript
"scripts": {
  "test": "jest --watchAll",
  "build": "webpack",
  "start": "webpack serve --config ./webpack.config.js --mode development"
},
```
![img-11]

## 11. Create webpack.config.js
Create webpack.config.js with following contents
```javascript
const HtmlWebpackPlugin = require('html-webpack-plugin');
const path = require("path");

module.exports = {
 mode: "development",
 entry: path.resolve(__dirname, './src/index.js'),
 target: 'web',
 module: {
   rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        loader: 'babel-loader'
      },
      {
        test: /\.css$/i,
        use:[
          'style-loader',
          'css-loader',
          'postcss-loader'
        ]
      }
    ]
  },
  resolve: {
    extensions: ['*', '.js', '.jsx']
  },
  output: {
    path: path.resolve(__dirname, './dist'),
    filename: 'bundle.js',
  },
  devServer: {
    port: '3030',
    static: path.resolve(__dirname, './public'),
    open: true,
    hot: true,
    liveReload: true
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: path.join(__dirname, 'public', 'index.html'),
    }),
  ],
};
```
![img-12]

## 12. Create tailwind.config.js
Creat tailwind.config.js with following contents
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./src/**/*.{html,js,jsx,ts,tsx}'],
  darkMode: 'class',
  theme: {
    fontFamily: {
      display: ['Open Sans', 'sans-serif'],
      body: ['Open Sans', 'sans-serif'],
    },
    extend: {},
  },
  plugins: [],
}

```
![img-13]
![img-14]

## 13. Create postcss.config.js
Create postcss.config.js with following contents
```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```
![img-15]

## 14. Create public folder
Create the public folder and index.html file with following contents.
```html
<!DOCTYPE html>
<html>
  <head>
    <title>My React App</title>
    <meta charset="utf-8">
  </head>
  <body>
    <div id="root"></div>
    <script src="bundle.js"></script>
  </body>
</html>
```
![img-16]
![img-18]

## 15. Create source folder
Create src folder with App.jsx, index.js and index.css files
```cmd
touch App.jsx index.js index.css
```
![img-19]

index.css
```javascript
@tailwind base;
@tailwind components;
@tailwind utilities;
```
![img-20
]
index.js
```javascript
import React from "react";
import ReactDOM from "react-dom/client";
import { App } from "./App";

import './index.css';

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <App />
);
```
![img-21]

App.jsx
```javascript
import React from "react";

export const App = () => {
  return(
    <div className="bg-gray-900 text-gray-200 h-screen">
      <Appointment value="Test" />
    </div>
  );
}
```
![img-22]

## 16. Create dist folder
Create dist folder and run build
```cmd
mkdir dist
```
```cmd
npm build
```
![img-23]

## 17. Run the project
```cmd
npm start
```

[img-01]: assets/img-01.png
[img-02]: assets/img-02.png
[img-03]: assets/img-03.png
[img-04]: assets/img-04.png
[img-05]: assets/img-05.png
[img-06]: assets/img-06.png
[img-07]: assets/img-07.png
[img-08]: assets/img-08.png
[img-09]: assets/img-09.png
[img-10]: assets/img-10.png
[img-11]: assets/img-11.png
[img-12]: assets/img-12.png
[img-13]: assets/img-13.png
[img-14]: assets/img-14.png
[img-15]: assets/img-15.png
[img-16]: assets/img-16.png
[img-17]: assets/img-17.png
[img-18]: assets/img-18.png
[img-19]: assets/img-19.png
[img-20]: assets/img-20.png
[img-21]: assets/img-21.png
[img-22]: assets/img-22.png
[img-23]: assets/img-23.png

