# [gulp](https://github.com/wearefractal/gulp)-apidoc [![Build Status](https://travis-ci.org/cobaimelan/gulp-apidoc.png?branch=master)](https://travis-ci.org/cobaimelan/gulp-apidoc)


> Generates a RESTful web API Documentation.
  Documentation at [apidocjs.com](http://apidocjs.com/)

Uses the [apidoc](https://github.com/apidoc/apidoc) library.

Is a fork of original gulp-apidoc because this was very urgent

## How It Works
`/path/api/stuff.js`:
```js
/**
 * @api {get} /user/:id Request User information
 * @apiName GetUser
 * @apiGroup User
 *
 * @apiParam {Number} id Users unique ID.
 *
 * @apiSuccess {String} firstname Firstname of the User.
 * @apiSuccess {String} lastname  Lastname of the User.
 */
```


## Install

Install with [npm](https://npmjs.org/package/gapidoc)

```
npm install --save-dev gapidoc
```


## Usage

```js
var gulp = require('gulp'),
    apidoc = require('gapidoc');

gulp.task('apidoc', function(){
          apidoc.exec({
            src: "example/",
            dest: "build/"
          });
});
```

With options:

```js
var gulp = require('gulp'),
    apidoc = require('gapidoc');

gulp.task('apidoc',function(){
              apidoc.exec({
	              src: "example/",
                  dest: "build/",
                  debug: true,
                  includeFilters: [ ".*\\.js$" ]
              });
});
```

Other options [checkout](https://github.com/apidoc/apidoc/blob/master/lib/apidoc.js#L15).


## API

### apidoc(options)


#### options.src

Type: `String`


#### options.dest

Type: `string`
Default: `doc/`

#### options.debug

Type: `Boolean`
Default: `false`

#### options.log

Type: `Boolean`
Default: `true`

#### options.includeFilters

Type: `Array`
Default: `[]`
