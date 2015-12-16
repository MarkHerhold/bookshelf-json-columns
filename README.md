# bookshelf-json-columns [![npm version][npm-image]][npm-url] [![build status][travis-image]][travis-url]

This [Bookshelf.js](https://github.com/tgriesser/bookshelf) plugin enables you to define which model columns have JSON format, stringifying its values before saving and parsing afterwards. It's recommended to use it with the `postgres` client, since bookshelf does not have schema information and doesn't know when to use `::json` building the knex queries. Through a simple configuration, there's no need to manually define hooks for each model with JSON columns.

## Installation

Install the package via `npm`:

```sh
$ npm install --save bookshelf-json-columns
```

## Usage

Require and register the `bookshelf-json-columns` plugin:

```js
var bookshelf = require('bookshelf')(knex);
var jsonColumns = require('bookshelf-json-columns');

bookshelf.plugin(jsonColumns);
```

Define which columns have JSON format with the `jsonColumns` prototype property:

```js
bookshelf.Model.extend({
  jsonColumns: ['foo', 'bar'],
  tableName: 'biz'
});
```

## Contributing

Feel free to fork this repository and submit pull requests. To run the tests, duplicate the `test/knexfile.js.dist` file, update it to your needs and run:

```sh
$ npm test
```

## License

MIT

[npm-image]: https://img.shields.io/npm/v/bookshelf-json-columns.svg?style=flat-square
[npm-url]: https://npmjs.org/package/bookshelf-json-columns
[travis-image]: https://img.shields.io/travis/seegno/bookshelf-json-columns.svg?style=flat-square
[travis-url]: https://travis-ci.org/seegno/bookshelf-json-columns