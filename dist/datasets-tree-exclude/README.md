<!--

@license Apache-2.0

Copyright (c) 2020 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->

# Datasets

> All stdlib datasets, except those which have a dedicated bundle, exposed as a tree namespace.

<section class="intro">

</section>

<!-- /.intro -->

<section class="usage">

## Usage

```javascript
var datasets = require( '@stdlib/dist-datasets-tree-exclude' ).datasets;
```

#### datasets.&lt;name&gt;( \[...args] )

Provides an interface to the dataset aliased according to `name`. Supported datasets may be determined by inspecting the enumerable property list

```javascript
var objectKeys = require( '@stdib/utils/keys' );

var props = objectKeys( datasets );
// returns [ ... ]
```

or by reading the [`@stdlib/datasets`][@stdlib/datasets] documentation.

For example, to access to the [AFINN-111][@stdlib/datasets/afinn-111] dataset,

```javascript
var dataset = datasets.AFINN_111();
```

To discover supported arguments for each dataset API, consult the documentation for the individual dataset, as can be found in the [`@stdlib/datasets`][@stdlib/datasets] namespace.

</section>

<!-- /.usage -->

* * *

<section class="notes">

## Notes

-   Unless an application depends on these datasets, they should **not** be sourced, and, if needed, consider bundling only those datasets which are necessary.

-   This package contains distributable files for use in browser environments or as shared ("vendored") libraries in server environments. Each distributable file is a standalone [UMD][umd] bundle which, if no recognized module system is present, will expose bundle contents to the global scope.

-   Each minified bundle has a corresponding [gzip][gzip]-compressed bundle. The [gzip][gzip] compression level for each compressed bundle is `9`, which is the highest (and most optimal) compression level. Deciding between uncompressed and compressed bundles depends on the application and whether compression is handled elsewhere in the application stack (e.g., [nginx][nginx], [CDN][cdn], _et cetera_).

-   While you are **strongly** encouraged to **vendor** bundles and host with a [CDN][cdn]/provider which can provide availability **guarantees**, especially for production applications, bundles are available via [unpkg][unpkg] for quick demos, proof-of-concepts, and instructional material. For example,

    ```html
    <script type="text/javascript" src="https://unpkg.com/@stdlib/dist-datasets-tree-exclude"></script>
    ```

    Please be mindful that [unpkg][unpkg] is a free, best-effort service relying on donated infrastructure which does **not** provide **any** availability guarantees. Under **no** circumstances should you **abuse** or **misuse** the service. You have been **warned**.

-   If you intend on embedding a standalone bundle **within** another bundle, you may need to rename `require` calls within the standalone bundle **before** bundling in order to maintain scoped module resolution. For example, if you plan on using [browserify][browserify] to generate a bundle containing embedded bundles, [browserify][browserify] plugins exist to "de-require" those bundles prior to bundling.

-   The bundles in this package exposes all [stdlib][stdlib] packages, except those which have a dedicated bundle, from the following namespace:

    -   [@stdlib/datasets][@stdlib/datasets]

</section>

<!-- /.notes -->

* * *

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var datasets = require( '@stdlib/dist-datasets-tree-exclude' ).datasets;

var words;
var dict;
var len;
var i;

words = datasets.AFINN_111();

// Convert to a dictionary...
len = words.length;
dict = {};
for ( i = 0; i < len; i++ ) {
    dict[ words[i][0] ] = words[i][1];
}
console.dir( dict );
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="/path/to/@stdlib/dist-datasets-tree-exclude/build/bundle.min.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope.

```html
<script type="text/javascript">
    // If no recognized module system present, exposed to global scope:
    var dataset = stdlib_datasets_tree_exclude.datasets.AFINN_111;
    console.log( dataset() );
</script>
```

</section>

<!-- /.examples -->

<section class="links">

[stdlib]: https://github.com/stdlib-js/stdlib

[@stdlib/datasets]: https://github.com/stdlib-js/stdlib/tree/develop/lib/node_modules/%40stdlib/datasets

[@stdlib/datasets/afinn-111]: https://github.com/stdlib-js/stdlib/tree/develop/lib/node_modules/%40stdlib/datasets/afinn-111

[umd]: https://github.com/umdjs/umd

[gzip]: https://en.wikipedia.org/wiki/Gzip

[nginx]: http://nginx.org/en/docs/

[cdn]: https://en.wikipedia.org/wiki/Content_delivery_network

[unpkg]: https://unpkg.com/#/

[browserify]: https://github.com/browserify/browserify

</section>

<!-- /.links -->
