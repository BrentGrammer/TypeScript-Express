# Typescript with Express.js

## Setup an Express project from scratch with TypeScript:

- `npm install -g typescript`
- `npm init -y`
- `tsc -init`
- `npm install express body-parser cookie-session`
- `npm install @types/express @types/body-parser @types/cookie-session`
- `npm install concurrently nodemon`
- Setup scripts in package.json:
  ```javascript
  "scripts": {
    "start:build": "tsc -w",
    "start:run": "nodemon build/index.js",
    "start": "concurrently npm:start:*"
  },
  ```

## Finding Types to use for Express:

- Ctrl/Command click on the express import statement to go to the type definition file (in node_modules/@types/)
- Search for the interface for the type you want to use (i.e. for Request or Response) in the file. Express exports these for you to import into your source code for use as named exports.
  Ex:

  ```javascript
  import express, { Request, Response } from express;

  app.get('/', (req: Request, res: Response) => {
    //code ...
  });
  ```
