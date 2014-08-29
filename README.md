# Angular CMS
This is a boilerplate CMS built with Angular, Twitter Bootstrap and Node; it is in development stage and aims to offer a quick start for creating full-stack angular application.

[![Build Status](https://travis-ci.org/jonniespratley/angular-cms.png)](https://travis-ci.org/jonniespratley/angular-cms)

[![Built with Grunt](https://cdn.gruntjs.com/builtwith.png)](http://gruntjs.com/)

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/jonniespratley/angular-cms/trend.png)](https://bitdeli.com/free "Bitdeli Badge")


## Technologies
Some featured technologies used in this project include the following:

* **MongoDB** - MongoDB is a document database that provides high performance,
high availability, and easy scalability.
* **NodeJS** - Node.js is a platform built on Chrome's JavaScript runtime for easily building fast, scalable network applications.
* **AngularJS** - AngularJS lets you write client-side web applications as if you had a smarter browser.
* **Bootstrap 3.0** - Bootstrap makes front-end web development faster and easier.
* **HTML5** - Using HTML5 in every way to make a better user experience.
* **Express** - Express is a minimal and flexible node.js web application framework, providing a robust set of features.
* **Karma Runner** - A simple tool that allows you to execute JavaScript code in multiple real browsers.
* **Protractor** - Protractor is an end-to-end test framework for AngularJS applications. Protractor built on top of WebDriverJS.






# Development


## Getting Started
To get started on developing with this code base you can either fork the repository or clone it using the following command:

```
$ git clone https://github.com/jonniespratley/angular-cms.git
```

### Step 1 - Install NPM dependencies
Before you can run or build the application you need to install the dependencies, execute the following command:

```
$ npm install
```

> **Note:** You may need to run this as a `sudo` user.


### Step 2 - Install Bower dependencies
Now you need to install the client-side dependencies that is managed by bower, execute the following command:

```
$ bower install
```

### Step 3 - Start Grunt server
Now you are ready to run the preview server that is used for development, execute the following command:

```
$ grunt serve
```

> **Note:** Your default browser should open up to [http://localhost:9000](http://localhost:9000)



## Running the application
To run the application on your local machine please take the following steps.


#### Step 1 - Start mongodb
To start mongodb execute the following command:

	$ sh ./bin/db.sh
	
> **Note:** If errors when executing command remove the `db/mongod.lock` file. 

#### Step 2 - Start REST server
To start the server execute the following command:

```
$ node server
```

> **Note:** The REST server is running at [http://localhost:8181/api/v2](http://localhost:8181/api/v2)





## Development
The following sections are different development tasks that I generally run while developing features.


### Karma Unit Tests
To run the Karma unit tests execute the following command:

```
$ grunt test
```

### Karma e2e Scenario Tests
To run the Karma scenario tests take the following steps:

1. Start Node server - `$ grunt serve`
2. Start REST server - `$ node server`
3. Start DB server - `$ sh bin/db.sh`
4. Now run the e2e tests by executing:

```
$ grunt test:e2e
```

> **Note:** Each step is a ‘new’ terminal window


### Protractor e2e Tests
To run the Protractor e2e tests take the following steps:

1. Start Node server - `$ grunt serve`
2. Start REST server - `$ node server`
3. Start DB server - `$ sh bin/db.sh`
4. Now run the Protractor tests by executing:

```
$ grunt protractor
```

> **Note:** Each step is a ‘new’ terminal window










---

## RESTful Server
The server is a Node.js server that supports dynamic RESTful API calls to resource endpoints. It will automatically create a database if it does not exist and collection(s). 

The base URL is `http://localhost:8181/api/v2`


HTTP  | METHOD | ENDPOINT
------------ | ------------- | ------------
 GET   |   findAll     |   /database/table
 GET   |   findById    |   /database/table/:id
 POST  |   add         |   /database/table
 PUT   |   update      |   /database/table/:id
 DELETE |  destroy     |   /database/table/:id

> **Tip:** To create new collection open `http://localhost:8181/api/v2/[DATABASE]/[COLLECTION]` in browser.

---


## WebSocket Server
This is a socket server implementation for "real" time.


### WebSocket Channels
These are the events that this socket server dispatches.


1. cms:authorization
2. cms:client:message
3. cms:client:connect
4. cms:client:disconnect
5. cms:server:message
6. cms:server:disconnect
7. cms:server:connect


---





## Themes
Themes will be installed via `bower`, search and install themes searching by tag `angular-cms`.

### Structure of theme
This is the structure of the themes.

```
my-theme/
	package.json
	bower.json
	css/
		my-theme.css
	js/
		my-theme.js
	index.html
	partials/
		header.html
		sidebar.html
		footer.html
		content.html
```		



---

## Plugins
Plugins will be installed via `bower`, search and install themes searching by tag `angular-cms`.

### Structure of plugin


---

## Documentation
The API documentation will be in the form of ngDocs style. The files located in the `content` directory are tutorial specs for the different features in this project. Documentation can be generated and viewed by running the following command:

```
$ grunt docs
```

> Your default browser should open [http://127.0.0.1:9191/#/api](http://127.0.0.1:9191/#/api)

## API Documentation
The following are diagrams of the concept behind this project repository.

![image](https://dl.dropboxusercontent.com/u/26906414/angular-cms/images/docs-classdiagram.png)

![image](https://dl.dropboxusercontent.com/u/26906414/angular-cms/images/docs-appmvc.png)
![image](https://dl.dropboxusercontent.com/u/26906414/angular-cms/images/docs-appanatomy.png)



_(Coming soon)_


---


## Important notes
Please don't edit files in the `dist` subdirectory as they are generated via Grunt. You'll find source code in the `app` subdirectory! Regarding code style like indentation and whitespace, **follow the conventions you see used in the source already.**


## Modifying the code
First, ensure that you have the latest [Node.js](http://nodejs.org/) and [npm](http://npmjs.org/) installed.

Test that Grunt's CLI and Bower are installed by running `grunt --version` and `bower --version`. 

1. Fork and clone the repo.
1. Run `npm install` to install all build dependencies (including Grunt).
1. Run `bower install` to install the front-end dependencies.
1. Run `grunt` to grunt this project.

Assuming that you don't see any red, you're ready to go. Just be sure to run `grunt` after making any changes, to ensure that nothing is broken.



## Submitting pull requests

1. Create a new branch, please don't work in your `master` branch directly.
1. Add failing tests for the change you want to make. Run `grunt` to see the tests fail.
1. Fix stuff.
1. Run `grunt` to see if the tests pass. Repeat steps 2-3 until done.
1. Update the documentation to reflect any changes.
1. Push to your fork and submit a pull request.

---

## TODO
The following list is features that are coming.

* user management & user roles
* action and view permissions
* i18n support on literals and object versions
* normalized database schema design
* some form of content import-export
* assets management and thumbnail generation for uploads
* Valid XHTML (compressed with GZIP)
* Rich text editing (e.g FCKeditor) which generates accessible markup
* search support
---

