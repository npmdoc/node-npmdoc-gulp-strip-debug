# api documentation for  [gulp-strip-debug (v1.1.0)](https://github.com/sindresorhus/gulp-strip-debug)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-strip-debug.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-strip-debug) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-strip-debug.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-strip-debug)
#### Strip console and debugger statements from JavaScript code

[![NPM](https://nodei.co/npm/gulp-strip-debug.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/gulp-strip-debug)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-strip-debug/build/screenCapture.buildCi.browser.apidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-strip-debug/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-strip-debug/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-strip-debug/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Sindre Sorhus",
        "url": "http://sindresorhus.com"
    },
    "bugs": {
        "url": "https://github.com/sindresorhus/gulp-strip-debug/issues"
    },
    "dependencies": {
        "gulp-util": "^3.0.0",
        "strip-debug": "^1.0.0",
        "through2": "^2.0.0"
    },
    "description": "Strip console and debugger statements from JavaScript code",
    "devDependencies": {
        "mocha": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "5d56b008452edf6823dadecb3e6254d06f3b5d3d",
        "tarball": "https://registry.npmjs.org/gulp-strip-debug/-/gulp-strip-debug-1.1.0.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "files": [
        "index.js"
    ],
    "gitHead": "bd1d6830a6962bbab0bcafec9c961d0d4747f379",
    "homepage": "https://github.com/sindresorhus/gulp-strip-debug",
    "keywords": [
        "gulpplugin",
        "strip",
        "remove",
        "delete",
        "clean",
        "debug",
        "debugger",
        "console",
        "log",
        "logging",
        "js",
        "javascript",
        "ecmascript",
        "ast",
        "esprima"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "sindresorhus"
        }
    ],
    "name": "gulp-strip-debug",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/sindresorhus/gulp-strip-debug.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "1.1.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-strip-debug](#apidoc.module.gulp-strip-debug)
1.  [function <span class="apidocSignatureSpan"></span>gulp-strip-debug ()](#apidoc.element.gulp-strip-debug.gulp-strip-debug)
1.  [function <span class="apidocSignatureSpan">gulp-strip-debug.</span>toString ()](#apidoc.element.gulp-strip-debug.toString)



# <a name="apidoc.module.gulp-strip-debug"></a>[module gulp-strip-debug](#apidoc.module.gulp-strip-debug)

#### <a name="apidoc.element.gulp-strip-debug.gulp-strip-debug"></a>[function <span class="apidocSignatureSpan"></span>gulp-strip-debug ()](#apidoc.element.gulp-strip-debug.gulp-strip-debug)
- description and source-code
```javascript
gulp-strip-debug = function () {
	return through.obj(function (file, enc, cb) {
		if (file.isNull()) {
			cb(null, file);
			return;
		}

		if (file.isStream()) {
			cb(new gutil.PluginError('gulp-strip-debug', 'Streaming not supported'));
			return;
		}

		try {
			file.contents = new Buffer(stripDebug(file.contents.toString()).toString());
			this.push(file);
		} catch (err) {
			this.emit('error', new gutil.PluginError('gulp-strip-debug', err, {fileName: file.path}));
		}

		cb();
	});
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.gulp-strip-debug.toString"></a>[function <span class="apidocSignatureSpan">gulp-strip-debug.</span>toString ()](#apidoc.element.gulp-strip-debug.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
...

		if (file.isStream()) {
			cb(new gutil.PluginError('gulp-strip-debug', 'Streaming not supported'));
			return;
		}

		try {
			file.contents = new Buffer(stripDebug(file.contents.toString()).toString());
			this.push(file);
		} catch (err) {
			this.emit('error', new gutil.PluginError('gulp-strip-debug', err, {fileName: file.path}));
		}

		cb();
	});
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
