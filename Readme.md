
# co-body

  Parse request bodies with generators inspired by [Raynos/body](https://github.com/Raynos/body).

## Installation

```
$ npm install co-body
```

## Options

  Available via [raw-body](https://github.com/stream-utils/raw-body/blob/master/index.js):

  - `limit` number or string representing the request size limit (1mb for json and 56kb for form-urlencoded)
  - `strict` When set to `true`, JSON parser will only accept arrays and objects; when `false` will accept anything `JSON.parse` accepts. Defaults to `true`.

## Example

```js
// application/json
var body = yield parse.json(req);

// explicit limit
var body = yield parse.json(req, { limit: '10kb' });

// application/x-www-form-urlencoded
var body = yield parse.form(req);

// either
var body = yield parse(req);
```

## Koa

  This lib also supports `ctx.req` in Koa (or other libraries),
  so that you may simply use `this` instead of `this.req`.

```js
// application/json
var body = yield parse.json(this);

// application/x-www-form-urlencoded
var body = yield parse.form(this);

// either
var body = yield parse(this);
```

# License

  MIT
