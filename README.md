# :zap: Node.js, mongoDB Shopping Cart

* Code to learn to learn Node.js. This is part of a Udemy Node.js course.
Code modified considerably to work with [MySQL Workbench database](https://dev.mysql.com/downloads/file/?id=480823) v8.0.13.0.msi.
* **Note:** to open web links in a new window use: _ctrl+click on link_

![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/nodejs-tutorial-shoppingcart?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/nodejs-tutorial-shoppingcart?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/nodejs-tutorial-shoppingcart?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/nodejs-tutorial-shoppingcart?style=plastic)

## :page_facing_up: Table of contents

* [:zap: Node.js, mongoDB Shopping Cart](#zap-nodejs-mongodb-shopping-cart)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-Do](#clipboard-status--to-do)
  * [Inspiration](#inspiration)
  * [:file_folder: License](#file_folder-license)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* Uses Embedded Javascript Templating ejs to create HTML markup with plain javascript.

## :camera: Screenshots

![screenprint](./images/.png)

## :signal_strength: Technologies

* [Node.js v14](https://nodejs.org)
* [Express v4](https://www.npmjs.com/package/express)
* [Sequelize v6](http://docs.sequelizejs.com) - adds promise-based Node.js Object Relational Mapping to MySQL. Features schema definition, schema synchronization/dropping, 1:1, 1:M & N:M Associations, through models, promises, hooks/callbacks/lifecycle events, prefetching/association including transactions, migrations and CLI (sequelize-cli).

## :floppy_disk: Setup

* `npm i` to install dependencies
* Start mysql
* to run on a dev server: type `nodemon app.js` then navigate to `localhost:3000`

## :computer: Code Examples

* `app.js` Sequelize method to sync with database then find user data by id or create new user etc.

```javascript
sequelize
  .sync() //sync with database
  .then((result) => {
    return User.findById(1);
    //console.log(result);
  })
  .then((user) => {
    if (!user) {
      return User.create({ name: "Max", email: "test@test.com" });
    }
    return user;
  })
  .then((user) => {
    // console.log(user);
    return user.createCart();
  })
  .then((cart) => {
    app.listen(3000);
  })
  .catch((err) => {
    console.log(err);
  });
```

## :cool: Features

* None

## :clipboard: Status & To-Do

* Status: Working
* To-Do: Nothing

## Inspiration

* [NodeJS - The Complete Guide (incl. MVC, REST APIs, GraphQL)](https://www.udemy.com/nodejs-the-complete-guide/)

## :file_folder: License

* This project is licensed under the terms of the MIT license.

## :envelope: Contact

* Repo created by [ABateman](https://github.com/AndrewJBateman), email: gomezbateman@yahoo.com
