<img width="75px" height="75px" align="right" alt="Create NodeJS Project Logo" src="https://raw.githubusercontent.com/nmicht/create-nodejs-project/master/assets/create-nodejs-project.png" title="Create NodeJS Project"/>

# Node Project Initializer

[![License][license-image]][license-url] [![version][npm-image]][npm-url]

An [npm initializer][npm/init] to scaffold a node project and include basic tools like lint, testing, etc.

> _`npm init <initializer>` can be used to set up a new or existing npm package._  
> _`initializer` in this case is an npm package named `create-<initializer>`, which will be installed by `npx`, and then have its main bin executed -- presumably creating or updating `package.json` and running any other initialization-related operations._  
> _[&mdash; Source: `docs.npmjs.com`][npm/init]_

## Requirements

- `npm >= 6.5`
- `node >= 10.1.0`

## Usage

1. Install the package as global
```
npm install -g create-nodejs-project
```

2. You will be prompted for your Github information  
If you do not have the information at the moment, you can keep it empty.  
In order to create projects with Github integration, you will need to add the authentication information later. See [Github Auth](#configure-Github-authentication)

3. Create your project
```
npm init nodejs-project path/to/new/project
```

## What it does

1. Create the folder for the new project
1. Guide you through a questionnarie to setup the project
2. Initialize a git repository
3. Copy the template files (src, eslintrc, gitignore, readme, etc)
4. Can create a Github repository
5. Handle the Github tokens for multiple accounts/users
5. Install eslint dependencies
5. Install the selected testing dependencies
6. Generate package.json with all the project details
7. Commit and push the initial commit

## About this package

The motivation started as a **DRY** thing.

I'm not expert with NodeJS, but every time that I start a new project, I hate to go to other project, copy files like eslintrc, editorconfig, install the same dependencies, create folder structure, etc.   

So, the idea is to have an automated way to initialize new NodeJS projects and with this have a new folder with everything ready to work in what really matters.  


## Future features

1. Unit testing
7. Options to create the project with params instead of questionnaire
10. A good error handler
11. Color for the console messages
12. Improve the template structure (the one that is generated in the new project) to include unit test
13. Include license files to the template copy/update process
18. Option to questionnaire with all the default values
2. Logic to handle multiple auth files and multiple github accounts

## Configure Github Authentication

If you are planning to allow this script to create your Github repositories, is required to generate a Github Token.

1. Visit https://github.com/settings/tokens.
2. Click Generate new token.
```
 Token Description: (your computer name)
 Scopes:
     [X] repo
         [X] repo:status
         [X] repo_deployment
         [X] public_repo
         [X] repo:invite
```
3. Click Generate token.
4. Copy the generated string to a safe place, such as a password safe.
5. Open Terminal and add the Github token.

```
# nano ~/create-nodejs-project.json

{
   "github": [
     {
       "user": "YOUR_USER",
       "token": "YOUR_TOKEN"
     },
     {
       "user": "OTHER_USER",
       "token": "OTHER_TOKEN"
     }
   ]
}
```



[license-url]: LICENSE
[license-image]: https://img.shields.io/github/license/nmicht/create-nodejs-project.svg?style=for-the-badge&logo=appveyor

[npm-url]: https://www.npmjs.com/package/create-nodejs-project
[npm-image]: https://img.shields.io/npm/v/create-nodejs-project.svg?style=for-the-badge&logo=npm

[npm/init]: https://docs.npmjs.com/cli/init#description
