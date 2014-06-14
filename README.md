oust [![Build Status](https://travis-ci.org/addyosmani/oust.svg?branch=master)](https://travis-ci.org/addyosmani/oust)
====

> Extract a list of stylesheets, scripts or HTML imports from HTML

### Install

```sh
npm install oust --save-dev
```

### Usage

First include:

```js
var oust = require('oust');
```

Resource links can then be extracted from either files:

#### Extract stylesheets references `<link rel="stylesheet">`

```js
var hrefs = oust({ src: 'test/sample/index.html' });
```

#### Extract script references `<script src>`

```js
var srcs = oust({ 
	src: 'test/sample/index.html', 
	selector: 'script', 
	attribute: 'src'
});
```

#### Extract HTML imports `<link rel="import">`

```js
var hrefs = oust({ 
	src: 'test/imports.html', 
	selector: 'link[rel="import"]', 
	attribute: 'href' 
});
```

#### Or from HTML string input:

```js
var hrefs = oust({ 
	source: '<html><link rel="stylesheet" href="styles/main.css"></html>' 
});
```

### API

#### Options

Attribute       | Default   | Description
---             | ---       | ---
`src`           | ``        | a valid path to the file you wish to parse
`source`        | ``        | a valid string to parse for references
`selector`      | `link[rel="stylesheet"]`        | a selector to query for
`attribute`        | `href`        | an attribute to read from the selector query

### License

Released under an Apache 2 license. © Google 2014.