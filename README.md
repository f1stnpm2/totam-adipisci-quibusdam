# @f1stnpm2/totam-adipisci-quibusdam <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES2017 spec-compliant `Object.entries` shim. Invoke its "shim" method to shim `Object.entries` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.github.io/ecma262/#sec-@f1stnpm2/totam-adipisci-quibusdam).

Most common usage:
```js
var assert = require('assert');
var entries = require('@f1stnpm2/totam-adipisci-quibusdam');

var obj = { a: 1, b: 2, c: 3 };
var expected = [['a', 1], ['b', 2], ['c', 3]];

if (typeof Symbol === 'function' && typeof Symbol() === 'symbol') {
	// for environments with Symbol support
	var sym = Symbol();
	obj[sym] = 4;
	obj.d = sym;
	expected.push(['d', sym]);
}

assert.deepEqual(entries(obj), expected);

if (!Object.entries) {
	entries.shim();
}

assert.deepEqual(Object.entries(obj), expected);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@f1stnpm2/totam-adipisci-quibusdam
[npm-version-svg]: https://versionbadg.es/f1stnpm2/totam-adipisci-quibusdam.svg
[deps-svg]: https://david-dm.org/f1stnpm2/totam-adipisci-quibusdam.svg
[deps-url]: https://david-dm.org/f1stnpm2/totam-adipisci-quibusdam
[dev-deps-svg]: https://david-dm.org/f1stnpm2/totam-adipisci-quibusdam/dev-status.svg
[dev-deps-url]: https://david-dm.org/f1stnpm2/totam-adipisci-quibusdam#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@f1stnpm2/totam-adipisci-quibusdam.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@f1stnpm2/totam-adipisci-quibusdam.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@f1stnpm2/totam-adipisci-quibusdam.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@f1stnpm2/totam-adipisci-quibusdam
[codecov-image]: https://codecov.io/gh/f1stnpm2/totam-adipisci-quibusdam/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/f1stnpm2/totam-adipisci-quibusdam/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/f1stnpm2/totam-adipisci-quibusdam
[actions-url]: https://github.com/f1stnpm2/totam-adipisci-quibusdam/actions
