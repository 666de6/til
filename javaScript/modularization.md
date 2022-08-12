<!--
 * @Author: Ada J
 * @Date: 2022-08-10 15:10:46
 * @LastEditTime: 2022-08-12 16:43:10
 * @Description:
-->

# What Are CJS, AMD, UMD, ESM, System, and IIFE?

## CJS (CommonJS)
> Suitable for Node and other bundlers (alias: commonjs).
```js
// importing
//importing from local dir
const doSomething = require('./doSomething.js'); 
//or importing from node_modules
const React = require('react');


//exporting
module.exports = function doSomething(n) {
  // do something
}
// or 
exports.a = "123"
```
* CJS imports module synchronously.
* You can import from a library node_modules or local dir. 
* CJS is widely used on server side. such as node.
* CJS module cannot be used on the browser side unless it is packaged with a transpiler, like Babel.

## AMD (Asynchronous Module Definition) 
> Used with module loaders like RequireJS.
```js
define(['dep1', 'dep2'], function (dep1, dep2) {
  //Define the module value by returning a value.
  return function () {};
});

// or
// "simplified CommonJS wrapping" https://requirejs.org/docs/whyamd.html
define(function (require) {
  var dep1 = require('dep1'),
      dep2 = require('dep2');
  return function () {};
});
```
* AMD was born out of CJS to support asynchronous module loading. 
* AMD syntax is less intuitive than CJS.
* AMD is used by RequireJS, working on the browser side.


UMD (Universal Module Definition)
> Works as amd, cjs, and iife all in one.
```js
(function (root, factory) {
    if (typeof define === "function" && define.amd) {
        define(["jquery", "underscore"], factory);
    } else if (typeof exports === "object") {
        module.exports = factory(require("jquery"), require("underscore"));
    } else {
        root.Requester = factory(root.$, root._);
    }
}(this, function ($, _) {
    // this is where I defined my module implementation
    var Requester = { 
      // ... 
    };
    return Requester;
}));
```
* UMD is designed to work everywhere — on the server side and the browser side.
* Unlike CJS or AMD, UMD is more like a pattern to configure several module systems.
* UMD is usually used as a fallback module when using bundler like Rollup/ Webpack.

ESM(ES6 Module) 
> Keep the bundle as an ES module file. Suitable for other bundlers and inclusion as a `<script type="module">` tag in modern browsers.
```js
// importing in index.js
//importing from local dir
import myLib from './mylib';
// or
import {foo, bar} from './myLib';
// importing from node_modules
import vue from 'vue';

...
// exporting in myLib.js
export default function() {
  // your Function
};
// or
export const foo() {...};
export const bar() {...};
```
or use in html
```html
<script type="module">
  import { foo } from 'my-lib'; // you can't import from a local file, that would be cause CORS error.
  foo();
</script>
```
* Works in many modern browsers.Since the version of `^12.20.0` || `^14.13.1` || `>=16.0.0`, Node starts to support ESM. ESM gains popularity to be used for both clients and servers.
* It has the best of both worlds: CJS-like simple syntax and AMD's async
* Tree-shakeable, due to ES6's static module structure

SYSTEM 
> Native format of the SystemJS loader (alias: systemjs).
```js
System.register([], function (exports) {
  'use strict';
  return {
    execute: function () {
      exports('power', power);

      function power(total, value) {
        return total ** value;
      }

    }
  };
});
```
* SystemJS is a universal module loader that supports CJS, AMD, and ESM modules. The bundler can bundle the code into SystemJS’s native format.

IIFE(Immediately Invoked Function Expression Module)
> A self-executing function suitable for inclusion as a `<script>` tag. If you want to create a bundle for your application, you probably want to use this.
```js
var example = (function (exports) {
  // doSomething...
  return exports;
}({}));
```
* It helps us to put things into namespaces to avoid variable collisions and keep code private.
