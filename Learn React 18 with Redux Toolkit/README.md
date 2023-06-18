# Learn React 18 with Redux Toolkit - Full Tutorial for Beginners

This course is in freeCodeCamp course.

YouTube : https://www.youtube.com/watch?v=2-crBg6wpp0

## Requirement

* HTML & CSS
* JavaScript

## Workflow

* Web Browser
* Text Editor - e.g. VS Code
  * VS Code download: https://code.visualstudio.com/
  * Instructor Setup VS Code: https://github.com/john-smilga/vs-code-setup-2022
* Terminal Command Line
  * OS
  * Integrated in VS Code
* NodeJS: https://nodejs.org/en
  * Recommend "LTS" version:
  * After install, checking node version in machine
  
    ```
    node --version
    ```
    
    ![check node version](https://github.com/jatu-studiobox/learn_react/assets/43282496/3b98279e-b23e-4c33-b597-3eba9c86950d)
    
  * When install nodejs, it include "npm" or "node package manager". For install external package
  
    ```
    npm install packageName
    ```
    
* Tool for create scraffolding ReactJS Project "vite", instead of "create-react-app".
  * Create React App website: https://create-react-app.dev/ for how to use create-react-app command.
    it use 'npx' for 'execute' command instead of install package
    
    ```
    npx create-react-app@latest appName
    ```
    
    ![create-react-app](https://github.com/jatu-studiobox/learn_react/assets/43282496/038c24ca-f9d6-4503-8f97-b7578963a4c0)

  * After create project by scraffolding, then open project in VS Code. And then test running project by running command in VS Code.
    
    ```
    npm start
    ```
    
    ![Project in VS Code](https://github.com/jatu-studiobox/learn_react/assets/43282496/74a456b7-d045-438e-bd49-e60f807ef60e)

    ![Running project command](https://github.com/jatu-studiobox/learn_react/assets/43282496/4e991a60-e418-47e0-9027-ad12d19622a5)

    When run 'npm start' command, development server will run at http://localhost:3000/
    
    ![Running app](https://github.com/jatu-studiobox/learn_react/assets/43282496/cb380129-9080-4612-8b85-4819aa34a615)

    While running development server with save edit code, output screen is hot reload. (page auto refresh with new code)
    
    ![edit code](https://github.com/jatu-studiobox/learn_react/assets/43282496/87d5ce95-2f49-444d-9e58-52d6e96ee2e9)

    ![hot reload](https://github.com/jatu-studiobox/learn_react/assets/43282496/2ddd135b-c70c-4c15-8d74-044063400a2c)

## Fundamentals
  * Instructor complete source code: https://github.com/john-smilga/react-course-v3
  * Course Fundamental: https://github.com/john-smilga/react-course-v3/tree/main/01-fundamentals
    for reference fundamental in this course.
  * Project folder struture. https://github.com/john-smilga/react-course-v3/tree/main/01-fundamentals#folder-structure
    
    ![project folder structure](https://github.com/jatu-studiobox/learn_react/assets/43282496/851ca443-0f5a-431c-b9fd-eca931a0c1e0)
    
    * **node_modules** folder - all dependencies our using in this project.
    * **public** folder - contains static assets including index.html, which basiccally is the things that to be served to the browser.
    * **src** folder - contains brain of our app, we do our work in here. Entry point of code is index.js, which inject to index.html, id=root.
    * **.gitignore** file - specific files will be ignore by source control (git)
    * **package.json** file - contain useful info about our project. interest 2 sections, 
      * *script* - running commmand in our project
      * *dependencies* - dependencies using in project
    * **README.md** file - info about project.

## Follow Fundamentals

#### Remove Boilerplate

- remove src folder
- create src folder
  - create index.js inside src

#### First Component

- Component in React is Javascript Function

```js
function Greeting() {
  return <h2>My First Component</h2>;
}

// arrow function also works

const Greeting = () => {
  return <h2>My First Component</h2>;
};
```

- starts with capital letter
- must return JSX (html)
- always close tag <Greeting/>

##### Typical Component

Must export component to outside.

```js
// imports or logic

const Greeting = () => {
  return <h2>My First Component</h2>;
};
export default Greeting;
```

##### Root Component (only one)

Root component have code different from other component, it has not export default, but it has createRoot and render.

index.js

```js
import React from 'react';
import ReactDOM from 'react-dom/client';

function Greeting() {
  return <h2>My First Component</h2>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));

root.render(<Greeting />);
```

How to create component by calling 'createElement'.

index.js

```js
const Greeting = () => {
  return React.createElement('h2', {}, 'hello world');
};
```

Above method is straightforward. But there is the problems, e.g. if we need 'h2' inside 'div' tag.

```html
<div>
 <h2>xxxxx</h2>
</div>
```

We must use nested 'createElement'. So, it is too long. see below. (If we need nested 20 or 50 tag ..)

```js
const Greeting = () => {
  return React.createElement(
    'div',
    {},
    React.createElement('h2', {}, 'hello world')
  );
};
```

So we should use JSX method instead for easier.

```js
function Greeting() {
  return (
    <div>
      <h2>hello world</h2>
    </div>
  );
}
```

#### JSX Rules
- return single element (one parent element) -> "ALWAYS"
  - semantics section/article
  - Fragment - let's us group elements without adding extra nodes
- example
```js
const Greeting = () => {
  return (
    <div>
      <h3>hello people</h3>
      <ul>
        <li><a href="#">hello world</a></li>
      </ul>
    </div>
  )
};
```

In case, need return more than single element, we must use 

Below, is React.Fragment component, for group elements without add html element extra node

```js
return <React.Fragment>...rest of the return</React.Fragment>;

// shorthand
return <>...rest of the return</>;
```
Example
```js
<React.Fragment>
  <h3>hello people</h3>
  <ul>
    <li><a href="#">hello world</a></li>
  </ul>
</React.Fragment>
```

- camelCase property naming convention
in JSX use camelCase "property" naming convension
```js
return (
  <div tabIndex={1}>
    <button onClick={myFunction}>click me</button>
    <label htmlFor='name'>Name</label>
    <input readOnly={true} id='name' />
  </div>
)
```

- "className" (JSX) instead of "class" (HTML)
```js
return <div className='someValue'>hello</div>;
```

- close every element
in JSX must always open & close tag, or self-close tag
```js
return <img />;
// or
return <input />;
```

- formatting
  - opening tag in the same line as return or ()
if does not use (), open tag must same line as return, but if use (...), no need to same line
```js
function Greeting() {
  return (
    <>
      <div className='someValue'>
        <h3>hello people</h3>
        <ul>
          <li>
            <a href='#'>hello world</a>
          </li>
        </ul>
      </div>
      <h2>hello world</h2>
      <input type='text' name='' id='' />
    </>
  );
}
```

```js
function Greeting() {
  return <h2>hello</h2>
  );
}
```
