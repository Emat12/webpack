# example.js

``` javascript
function getTemplate(templateName, callback) {
	require.ensure([], function(require) {
		callback(require("../require.context/templates/"+templateName)());
	});
}
getTemplate("a", function(a) {
	console.log(a);
});
getTemplate("b", function(b) {
	console.log(b);
});
```

# js/output.js

``` javascript
/******/ (function(modules) { // webpackBootstrap
/******/ 	// install a JSONP callback for chunk loading
/******/ 	var parentJsonpFunction = window["webpackJsonp"];
/******/ 	window["webpackJsonp"] = function webpackJsonpCallback(chunkIds, moreModules, executeModule) {
/******/ 		// add "moreModules" to the modules object,
/******/ 		// then flag all "chunkIds" as loaded and fire callback
/******/ 		var moduleId, chunkId, i = 0, resolves = [];
/******/ 		for(;i < chunkIds.length; i++) {
/******/ 			chunkId = chunkIds[i];
/******/ 			if(installedChunks[chunkId])
/******/ 				resolves.push(installedChunks[chunkId][0]);
/******/ 			installedChunks[chunkId] = 0;
/******/ 		}
/******/ 		for(moduleId in moreModules) {
/******/ 			modules[moduleId] = moreModules[moduleId];
/******/ 		}
/******/ 		if(parentJsonpFunction) parentJsonpFunction(chunkIds, moreModules);
/******/ 		while(resolves.length)
/******/ 			resolves.shift()();

/******/ 	};

/******/ 	// The module cache
/******/ 	var installedModules = {};

/******/ 	// objects to store loaded and loading chunks
/******/ 	var installedChunks = {
/******/ 		1: 0
/******/ 	};

/******/ 	// The require function
/******/ 	function __webpack_require__(moduleId) {

/******/ 		// Check if module is in cache
/******/ 		if(installedModules[moduleId])
/******/ 			return installedModules[moduleId].exports;

/******/ 		// Create a new module (and put it into the cache)
/******/ 		var module = installedModules[moduleId] = {
/******/ 			exports: {},
/******/ 			id: moduleId,
/******/ 			loaded: false
/******/ 		};

/******/ 		// Execute the module function
/******/ 		modules[moduleId].call(module.exports, module, module.exports, __webpack_require__);

/******/ 		// Flag the module as loaded
/******/ 		module.loaded = true;

/******/ 		// Return the exports of the module
/******/ 		return module.exports;
/******/ 	}

/******/ 	// This file contains only the entry chunk.
/******/ 	// The chunk loading function for additional chunks
/******/ 	__webpack_require__.e = function requireEnsure(chunkId) {
/******/ 		if(installedChunks[chunkId] === 0)
/******/ 			return Promise.resolve()

/******/ 		// an Promise means "currently loading".
/******/ 		if(installedChunks[chunkId]) {
/******/ 			return installedChunks[chunkId][2];
/******/ 		}
/******/ 		// start chunk loading
/******/ 		var head = document.getElementsByTagName('head')[0];
/******/ 		var script = document.createElement('script');
/******/ 		script.type = 'text/javascript';
/******/ 		script.charset = 'utf-8';
/******/ 		script.async = true;
/******/ 		script.timeout = 120000;

/******/ 		script.src = __webpack_require__.p + "" + chunkId + ".js";
/******/ 		var timeout = setTimeout(onScriptComplete, 120000);
/******/ 		script.onerror = script.onload = onScriptComplete;
/******/ 		function onScriptComplete() {
/******/ 			// avoid mem leaks in IE.
/******/ 			script.onerror = script.onload = null;
/******/ 			clearTimeout(timeout);
/******/ 			var chunk = installedChunks[chunkId];
/******/ 			if(chunk !== 0) {
/******/ 				if(chunk) chunk[1](new Error('Loading chunk ' + chunkId + ' failed.'));
/******/ 				installedChunks[chunkId] = undefined;
/******/ 			}
/******/ 		};
/******/ 		head.appendChild(script);

/******/ 		var promise = new Promise(function(resolve, reject) {
/******/ 			installedChunks[chunkId] = [resolve, reject];
/******/ 		});
/******/ 		return installedChunks[chunkId][2] = promise;
/******/ 	};

/******/ 	// expose the modules object (__webpack_modules__)
/******/ 	__webpack_require__.m = modules;

/******/ 	// expose the module cache
/******/ 	__webpack_require__.c = installedModules;

/******/ 	// __webpack_public_path__
/******/ 	__webpack_require__.p = "js/";

/******/ 	// on error function for async loading
/******/ 	__webpack_require__.oe = function(err) { throw err; };

/******/ 	// Load entry module and return exports
/******/ 	return __webpack_require__(__webpack_require__.s = 0);
/******/ })
/************************************************************************/
/******/ ([
/* 0 */
/*!********************!*\
  !*** ./example.js ***!
  \********************/
/***/ function(module, exports, __webpack_require__) {

	function getTemplate(templateName, callback) {
		__webpack_require__.e/* nsure */(0).catch(function(err) { __webpack_require__.oe(err); }).then(function(require) {
			callback(__webpack_require__(/*! ../require.context/templates */ 1)("./"+templateName)());
		}.bind(null, __webpack_require__));
	}
	getTemplate("a", function(a) {
		console.log(a);
	});
	getTemplate("b", function(b) {
		console.log(b);
	});

/***/ }
/******/ ]);
```

# js/0.js

``` javascript
webpackJsonp([0],[
/* 0 */,
/* 1 */
/*!*********************************************!*\
  !*** ../require.context/templates ^\.\/.*$ ***!
  \*********************************************/
/***/ function(module, exports, __webpack_require__) {

	var map = {
		"./a": 2,
		"./a.js": 2,
		"./b": 3,
		"./b.js": 3,
		"./c": 4,
		"./c.js": 4
	};
	function webpackContext(req) {
		return __webpack_require__(webpackContextResolve(req));
	};
	function webpackContextResolve(req) {
		var id = map[req];
		if(!(id + 1)) // check for number
			throw new Error("Cannot find module '" + req + "'.");
		return id;
	};
	webpackContext.keys = function webpackContextKeys() {
		return Object.keys(map);
	};
	webpackContext.resolve = webpackContextResolve;
	module.exports = webpackContext;
	webpackContext.id = 1;


/***/ },
/* 2 */
/*!*****************************************!*\
  !*** ../require.context/templates/a.js ***!
  \*****************************************/
/***/ function(module, exports) {

	module.exports = function() {
		return "This text was generated by template A";
	}

/***/ },
/* 3 */
/*!*****************************************!*\
  !*** ../require.context/templates/b.js ***!
  \*****************************************/
/***/ function(module, exports) {

	module.exports = function() {
		return "This text was generated by template B";
	}

/***/ },
/* 4 */
/*!*****************************************!*\
  !*** ../require.context/templates/c.js ***!
  \*****************************************/
/***/ function(module, exports) {

	module.exports = function() {
		return "This text was generated by template C";
	}

/***/ }
]);
```

# Info

## Uncompressed

```
Hash: 960f23ddeec29787cc42
Version: webpack 2.0.6-beta
Time: 99ms
    Asset     Size  Chunks             Chunk Names
     0.js  1.65 kB       0  [emitted]  
output.js  4.65 kB       1  [emitted]  main
chunk    {0} 0.js 463 bytes {1} [rendered]
    > [0] ./example.js 2:1-4:3
    [1] ../require.context/templates ^\.\/.*$ 217 bytes {0} [built]
        cjs require context ../require.context/templates [0] ./example.js 3:11-64
    [2] ../require.context/templates/a.js 82 bytes {0} [optional] [built]
        context element ./a [1] ../require.context/templates ^\.\/.*$
        context element ./a.js [1] ../require.context/templates ^\.\/.*$
    [3] ../require.context/templates/b.js 82 bytes {0} [optional] [built]
        context element ./b [1] ../require.context/templates ^\.\/.*$
        context element ./b.js [1] ../require.context/templates ^\.\/.*$
    [4] ../require.context/templates/c.js 82 bytes {0} [optional] [built]
        context element ./c [1] ../require.context/templates ^\.\/.*$
        context element ./c.js [1] ../require.context/templates ^\.\/.*$
chunk    {1} output.js (main) 276 bytes [rendered]
    > main [0] ./example.js 
    [0] ./example.js 276 bytes {1} [built]
```

## Minimized (uglify-js, no zip)

```
Hash: 960f23ddeec29787cc42
Version: webpack 2.0.6-beta
Time: 165ms
    Asset       Size  Chunks             Chunk Names
     0.js  544 bytes       0  [emitted]  
output.js    1.14 kB       1  [emitted]  main
chunk    {0} 0.js 463 bytes {1} [rendered]
    > [0] ./example.js 2:1-4:3
    [1] ../require.context/templates ^\.\/.*$ 217 bytes {0} [built]
        cjs require context ../require.context/templates [0] ./example.js 3:11-64
    [2] ../require.context/templates/a.js 82 bytes {0} [optional] [built]
        context element ./a [1] ../require.context/templates ^\.\/.*$
        context element ./a.js [1] ../require.context/templates ^\.\/.*$
    [3] ../require.context/templates/b.js 82 bytes {0} [optional] [built]
        context element ./b [1] ../require.context/templates ^\.\/.*$
        context element ./b.js [1] ../require.context/templates ^\.\/.*$
    [4] ../require.context/templates/c.js 82 bytes {0} [optional] [built]
        context element ./c [1] ../require.context/templates ^\.\/.*$
        context element ./c.js [1] ../require.context/templates ^\.\/.*$
chunk    {1} output.js (main) 276 bytes [rendered]
    > main [0] ./example.js 
    [0] ./example.js 276 bytes {1} [built]
```
