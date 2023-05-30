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
