# npmtest-topojson

#### basic test coverage for  [topojson (v3.0.0)](https://github.com/topojson/topojson)  [![npm package](https://img.shields.io/npm/v/npmtest-topojson.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-topojson) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-topojson.svg)](https://travis-ci.org/npmtest/node-npmtest-topojson)

#### An extension to GeoJSON that encodes topology.

[![NPM](https://nodei.co/npm/topojson.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/topojson)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-topojson/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-topojson/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-topojson/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-topojson/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-topojson/build/test-report.html)|
| test-server-github : | [![github.com test-server](https://npmtest.github.io/node-npmtest-topojson/GitHub-Mark-32px.png)](https://npmtest.github.io/node-npmtest-topojson/build/app/index.html) | | build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-topojson/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-topojson/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-topojson/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-topojson/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-topojson/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-topojson/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-topojson/build/test-report.html](https://npmtest.github.io/node-npmtest-topojson/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-topojson/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-topojson/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-topojson/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-topojson/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-topojson/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-topojson/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-topojson/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-topojson/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Mike Bostock",
        "url": "https://bost.ocks.org/mike"
    },
    "bin": {
        "geo2topo": "node_modules/topojson-server/bin/geo2topo",
        "toposimplify": "node_modules/topojson-simplify/bin/toposimplify",
        "topo2geo": "node_modules/topojson-client/bin/topo2geo",
        "topomerge": "node_modules/topojson-client/bin/topomerge",
        "topoquantize": "node_modules/topojson-client/bin/topoquantize"
    },
    "browser": "dist/topojson.js",
    "bugs": {
        "url": "https://github.com/topojson/topojson/issues"
    },
    "dependencies": {
        "topojson-client": "3.0.0",
        "topojson-server": "3.0.0",
        "topojson-simplify": "3.0.0"
    },
    "description": "An extension to GeoJSON that encodes topology.",
    "devDependencies": {
        "package-preamble": "0.0",
        "rollup": "0.41",
        "rollup-plugin-ascii": "0.0",
        "rollup-plugin-node-resolve": "2",
        "tape": "4",
        "uglify-js": "2"
    },
    "directories": {},
    "dist": {
        "shasum": "c2aca1b76435e801dce3f229586bbd5767115ce3",
        "tarball": "https://registry.npmjs.org/topojson/-/topojson-3.0.0.tgz"
    },
    "gitHead": "ccd0bcad70bb837d27d14b9524c0bffb3ae41d19",
    "homepage": "https://github.com/topojson/topojson",
    "jsnext:main": "index",
    "keywords": [
        "topojson",
        "geojson"
    ],
    "license": "BSD-3-Clause",
    "main": "dist/topojson.node.js",
    "maintainers": [
        {
            "name": "mbostock"
        },
        {
            "name": "jasondavies"
        }
    ],
    "module": "index",
    "name": "topojson",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/topojson/topojson.git"
    },
    "scripts": {
        "postpublish": "git push && git push --tags && cp -v README.md LICENSE.md dist/topojson.js dist/topojson.min.js ../topojson-bower && cd ../topojson-bower && git add README.md LICENSE.md topojson.js topojson.min.js && git commit -m \"${npm_package_version}\" && git tag -am \"${npm_package_version}\" v${npm_package_version} && git push && git push --tags && cd - && cp dist/topojson.js ../d3.github.com/topojson.v3.js && cp dist/topojson.min.js ../d3.github.com/topojson.v3.min.js && cd ../d3.github.com && git add topojson.v3.js topojson.v3.min.js && git commit -m \"topojson ${npm_package_version}\" && git push && cd - && zip -j dist/topojson.zip -- LICENSE.md README.md dist/topojson.js dist/topojson.min.js",
        "prepublish": "npm run test && rollup -c --banner \"$(preamble)\" -f umd -n topojson -o dist/topojson.js -- index.js && uglifyjs --preamble \"$(preamble)\" dist/topojson.js -c negate_iife=false -m -o dist/topojson.min.js",
        "pretest": "rm -rf dist && mkdir dist && node rollup.node",
        "test": "tape 'test/**/*-test.js'"
    },
    "version": "3.0.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
