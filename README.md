# Libxmljs

LibXML bindings for [node.js](http://nodejs.org/)

    var libxmljs = require("libxmljs");
    var xml =  '<?xml version="1.0" encoding="UTF-8"?>' +
               '<root>' +
                   '<child foo="bar">' +
                       '<grandchild baz="fizbuzz">grandchild content</grandchild>' +
                   '</child>' +
                   '<sibling>with content!</sibling>' +
               '</root>';

    var xmlDoc = libxmljs.parseXmlString(xml);

    // xpath queries
    var gchild = xmlDoc.get('//grandchild');

    console.log(gchild.text());  // prints "grandchild content"

    var children = xmlDoc.root().childNodes();
    var child = children[0];

    console.log(child.attr('foo').value()); // prints "bar"

## Basics

* GitHub Repo - [http://github.com/polotek/libxmljs](http://github.com/polotek/libxmljs)
* Docs - [http://github.com/polotek/libxmljs/wiki](http://github.com/polotek/libxmljs/wiki)
* Mailing list - [http://groups.google.com/group/libxmljs](http://groups.google.com/group/libxmljs)

## API and Examples

Check out the wiki [http://github.com/polotek/libxmljs/wiki](http://github.com/polotek/libxmljs/wiki)

## Requirements

* [libxml2](http://www.xmlsoft.org/)
* [node.js](http://nodejs.org/)

**pre-conditions**

You will need have the libxml2 library installed and also the libxml2-devel
package. This comes with the `xml2-config` utility that is needed for
compiling.  **This command must be in your path.**

## Installation

**npm**

For the upstream version:
    npm install libxmljs

For my fork:
    npm install https://github.com/shtylman/libxmljs/tarball/master

**from source**

In the root of the source directory, just run `npm install`.  This will
generate the required binaries for library functionality. You can then
use `npm link` or copy the source folder to a `node_modules` directory

**tests**

    make test

    make test-verbose
