acorn-walkall
=====================

acorn-walkall provides a custom walker for Marijn Haverbeke's [acorn JavaScript
parser](http://marijnhaverbeke.nl/acorn/) that traverses all AST nodes.

Documentation: [acorn-walkall on Sourcegraph](https://sourcegraph.com/repos/github.com/sourcegraph/acorn-walkall)


Usage
-----

```javascript
var acorn = require('acorn'),
    walk = require('acorn/util/walk'),
    walkall = require('./walkall');
var ast = acorn.parse('var x = 7;');
walk.simple(ast, walkall.makeVisitors(function(node) {
  console.log('Found node type', node.type);
}), walkall.traversers);
```

The included `bin/walkall` script emits the AST node type and source location for each AST node in
the specified JavaScript file.

Running tests
-------------

Run `npm test`.


Author
---------------------

* [Quinn Slack](mailto:sqs@sourcegraph.com)
