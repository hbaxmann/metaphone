# metaphone [![Build Status](https://img.shields.io/travis/wooorm/metaphone.svg?style=flat)](https://travis-ci.org/wooorm/metaphone) [![Coverage Status](https://img.shields.io/coveralls/wooorm/metaphone.svg?style=flat)](https://coveralls.io/r/wooorm/metaphone?branch=master)

[Metaphone](http://en.wikipedia.org/wiki/metaphone) algorithm in JavaScript. No cruft. Real fast.

## Installation

npm:
```sh
$ npm install metaphone
```

Component:
```sh
$ component install wooorm/metaphone
```

Bower:
```sh
$ bower install metaphone
```

## Usage

```js
var metaphone = require('metaphone');

metaphone("hiccups"); // "HKKPS"
metaphone("detestable"); // "TTSTBL"
metaphone("vileness"); // "FLNS"
metaphone("detestable") === metaphone("tetestble"); // true
```

With [stemmer](https://github.com/wooorm/stemmer):
```js
var metaphone = require('metaphone');
var stemmer = require('stemmer');

metaphone(stemmer("hiccups")); // HKKP
metaphone(stemmer("detestable")); // TTST
metaphone(stemmer("vileness")); // FL

metaphone(stemmer("detestable")) === metaphone(stemmer("tetest")); // true
```

## CLI

Install:
```sh
$ npm install --global metaphone
```

Use:
```
Usage: metaphone [options] string

Fast Metaphone implementation

Options:

  -h, --help           output usage information
  -v, --version        output version number

Usage:

# output phonetics of given value
$ metaphone detestable
# TTSTBL

# output phonetics from stdin
$ echo "vileness" | metaphone
# FLNS
```

## Benchmark

On a MacBook Air, it runs about 136,000 op/s, which is a bit faster than natural.

```
           metaphone — this module
  136 op/s » op/s * 1,000

           natural — more options
  113 op/s » op/s * 1,000

           Katee/metafone — pretty buggy
   45 op/s » op/s * 1,000
```

## License

MIT © [Titus Wormer](http://wooorm.com)
