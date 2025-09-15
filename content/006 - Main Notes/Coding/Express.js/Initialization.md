
2025-03-26  14:38

Status: #adult

Tags: #backend #computer-science #expressjs

# Setting up the Server

## Index.mjs

```js
import express from "express"

const app = express();

const PORT = process.env.PORT || 3000;

app.listen(PORT, () => {

console.log(`Server running on port ${PORT}`);

});

```

## Package.json


``` js
{

"name": "expressjs-tutorial",

"version": "1.0.0",

"main": "index.mjs",

"type": "module",

"scripts": {

"test": "echo \"Error: no test specified\" && exit 1",

"start:dev": "nodemon ./src/index.mjs",

"start": "node ./src/index.mjs"

},

"keywords": [],

"author": "",

"license": "ISC",

"description": "",

"dependencies": {

"express": "^4.21.2",

"nodemon": "^3.1.9"

}

}

```
## References

[Anson](https://www.youtube.com/watch?v=nH9E25nkk3I&t=15369s)

