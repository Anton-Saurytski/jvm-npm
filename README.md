# jvm-npm

Support for NPM module loading in Javascript runtimes on the JVM.
Implementation is based on http://nodejs.org/api/modules.html and
should be fully compatible. This, of course, does not include the
full node.js API, so don't expect all of the standard NPM modules
that depend on it to work. If you want to use existing NPM modules
that depend on the Node.js API, consider the not-yet-fully-baked
[nodyn project](http://nodyn.io). If you are writing your own NPM
modules in DynJS, Rhino or Nashorn, this should work just fine.

This module is known to work with DynJS, and has been briefly tested
on Nashorn, and should work with Rhino as well. 

## Usage

Using the global `load()` functions supplied by DynJS, Nashorn and
Rhino, load `npm_modules.js` into the global execution context:

    dynjs> load('./npm_modules.js');
    dynjs> var x = require('some_module');

Or with Nashorn:

    nashorn> load('./npm_modules.js');
    nashorn> var x = require('some_module');


