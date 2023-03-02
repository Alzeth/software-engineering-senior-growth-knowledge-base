RequireJS implements the AMD API [(source)](http://www.requirejs.org/docs/whyamd.html).

CommonJS is a way of defining modules with the help of an exports object, that defines the module contents.
Simply put, a CommonJS implementation might work like this:

```
// someModule.js
exports.doSomething = function() { return "foo"; };

//otherModule.js
var someModule = require('someModule'); // in the vein of node    
exports.doSomethingElse = function() { return someModule.doSomething() + "bar"; };
```

Basically, CommonJS specifies that you need to have a require() function to fetch dependencies, an exports variable to export module
contents and a module identifier (which describes the location of the module in question in relation to this module)
that is used to require the dependencies [(source)](http://wiki.commonjs.org/wiki/Modules/1.1.1). CommonJS has various implementations,
including Node.js, which you mentioned.

CommonJS was not particularly designed with browsers in mind, so it doesn't fit in the browser environment very well
(*I really have no source for this--it just says so everywhere, including [the RequireJS site](http://requirejs.org/docs/commonjs.html).*)
Apparently, this has something to do with asynchronous loading, etc.

On the other hand, RequireJS implements AMD, which is designed to suit the browser environment [(source)](https://github.com/amdjs/amdjs-api/wiki/AMD). Apparently,
AMD started as a spinoff of the CommonJS Transport format and evolved into its own module definition API.
Hence the similarities between the two. The new feature in AMD is the define() function that allows the module to declare its dependencies
before being loaded. For example, the definition could be:

```
define('module/id/string', ['module', 'dependency', 'array'], 
function(module, factory function) {
  return ModuleContents;  
});
```

So, CommonJS and AMD are JavaScript module definition APIs that have different implementations, but both come from the same origins.

AMD is more suited for the browser, because it supports asynchronous loading of module dependencies.
RequireJS is an implementation of AMD, while at the same time trying to keep the spirit of CommonJS (mainly in the module identifiers).
To confuse you even more, RequireJS, while being an AMD implementation, offers a CommonJS wrapper so CommonJS modules can almost directly
be imported for use with RequireJS.

```
define(function(require, exports, module) {
  var someModule = require('someModule'); // in the vein of node    
  exports.doSomethingElse = function() { return someModule.doSomething() + "bar"; };
});
```


>> https://stackoverflow.com/questions/16521471/relation-between-commonjs-amd-and-requirejs
