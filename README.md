# oledb.js

[![npm version](https://img.shields.io/badge/npm-v1.1.1-blue.svg)](https://www.npmjs.com/package/oledb)
[![license](https://img.shields.io/badge/license-MIT-orange.svg)](LICENSE)
[![tips](https://img.shields.io/badge/tips-bitcoin-brightgreen.svg)](https://www.coinbase.com/blahyourhamster)

A small **promise based** module which uses [Edge](https://github.com/tjanczuk/edge) to connect and execute queries for an [OLE DB](https://en.wikipedia.org/wiki/OLE_DB).

## Example
```
const connectionString = 'provider=vfpoledb;data source=C:/MyDatabase.dbc';

const oledb = require('oledb');
const db = oledb(connectionString);

let command = 'select * from account';

db.query(command)
.then(function(results) {
    console.log(results[0]);
},
function(error) {
    console.error(error);
});
```

## Promises
There are 3 available promises exposed by the module:

- `.query(command)` - Executes a query and returns the result set returned by the query as an array.
- `.execute(command)` - Executes a query command and returns the number of rows affected.
- `.scalar(command)` - Executes the query and returns the first column of the first row in the result set returned by the query. All other columns and rows are ignored.

*Where `command` is the query string.*

## Installation
```
npm install oledb --save
```

## License
This project is licensed under [MIT](LICENSE).
