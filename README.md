# Polyfiller catalog

[![npm version](https://badge.fury.io/js/polyfiller-catalog.svg)](http://badge.fury.io/js/polyfiller-catalog)
[![Build Status](https://travis-ci.org/Polyfiller/polyfiller-catalog.png)](https://travis-ci.org/Polyfiller/polyfiller-catalog)
[![Dependency Status](https://david-dm.org/Polyfiller/polyfiller-catalog.svg)](https://david-dm.org/Polyfiller/polyfiller-catalog)
[![Donate](https://img.shields.io/gratipay/polyfiller.corp.svg)](https://gratipay.com/polyfiller.corp)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE.txt)


> A database for polyfill combinators

## Getting Started

This package requires Node `~0.10.0`

If you haven't used [npm](https://www.npmjs.com/) before, be sure to check out the [Getting Started](https://nodejs.org/community/) guide, as it explains how to install [npm](https://docs.npmjs.com/getting-started/installing-node) and use a [package.json](https://docs.npmjs.com/files/package.json) file. 
Once you're familiar with that process, you may install this package with this command:

```shell
npm install polyfiller --save-dev
```

Once the package has been installed, it may be used inside your files with this line of JavaScript:

```js
var catalog = require('polyfiller-catalog');
```


### Usage Example

```js
catalog(); // returns an absolute path to the catalog
```


### Tests

```
grunt test
```

### Structure

Required file structure;

```
catalog
	Promise
		index.json
		index.js
```

**index.json**

```json
{
	"name": "Promise"
}
```

There are dependencies?

```
"dependencies": ["window.setImmediate"]
```

**index.js**

```js
module.exports = [
	{
		type: 'npm',
		name: 'es6-promises'
	}
];
```

The files are located locally?

```
catalog
	Promise
		files
			index.js — your polyfill

		index.json
		index.js
```

```js
var path = require('path');

module.exports = [
	{
		type: 'file',
		name: path.join(__dirname, './files/index.js')
	}
];
```


### Contributing

1. Fork the one
2. Create a topic branch
3. Make your commits
4. Write the tests and run `grunt test`
4. Run `grunt build`
5. Submit Pull Request once Tests are Passing


### License

MIT

Task submitted by [Alexander Abashkin](https://github.com/monolithed)
