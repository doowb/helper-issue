# helper-issue [![NPM version](https://badge.fury.io/js/helper-issue.svg)](http://badge.fury.io/js/helper-issue)  [![Build Status](https://travis-ci.org/helpers/helper-issue.svg)](https://travis-ci.org/helpers/helper-issue)

> Create a url to prepopulate a github issue.

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i helper-issue --save
```

## Usage

```js
var issue = require('helper-issue');
```

## API

### [issue](index.js#L37)

Helper to create a URL that will prepopulate a github issue.

**Params**

* `options` **{Object}**: Options containing values to use or a hash (when used with Handlebars) with values to use.
* `options.owner` **{String}**: Repository owner (either github user or org).
* `options.repo` **{String}**: Repository name (if owner is omitted, provide full repository name).
* `options.title` **{String}**: Short string to populate the github issue title field.
* `options.body` **{String}**: Markdown string to populate the github issue body field.
* `returns` **{String}**: URL that can be used in an anchor tag.

**Example**

```js
var url = issue({
  owner: 'helper',
  repo: 'helper-issue',
  title: 'Issue Title',
  body: 'Issue body that may contain markdown'
});
//=> https://github.com/helper/helper-issue/issues/new?title=Issue%20Title&body=Issue%20body%20that%20may%20contain%20markdown
```

### [.toHandlebars](index.js#L68)

Wrap `issue` to allow using in handlebars (applies Handlebars.SafeString() to the url)

* `returns` **{Function}**: Function usable as a helper in Handlebars

**Example**

```js
var Handlebars = require('handlebars');
Handlebars.registerHelper('issue', issue.toHandlebars());
```

## Related projects

## Running tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/helpers/helper-issue/issues/new).

## Author

**Brian Woodward**

+ [github/doowb](https://github.com/doowb)
+ [twitter/doowb](http://twitter.com/doowb)

## License

Copyright © 2015 Brian Woodward
Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on September 03, 2015._