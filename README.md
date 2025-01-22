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


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# ternary

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> C APIs for registering a Node-API module exporting interfaces for invoking ternary numerical functions.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/math-base-napi-ternary
```

</section>

<section class="usage">

## Usage

```javascript
var headerDir = require( '@stdlib/math-base-napi-ternary' );
```

#### headerDir

Absolute file path for the directory containing header files for C APIs.

```javascript
var dir = headerDir;
// returns <string>
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

```javascript
var headerDir = require( '@stdlib/math-base-napi-ternary' );

console.log( headerDir );
// => <string>
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/math/base/napi/ternary.h"
```

<!-- NOTE: keep in alphabetical order according to the suffix XXX_X -->

#### STDLIB_MATH_BASE_NAPI_MODULE_DDD_D( fcn )

Macro for registering a Node-API module exporting an interface for invoking a ternary function accepting and returning double-precision floating-point numbers.

```c
static double add( const double x, const double y, const double z ) {
    return x + y + z;
}

// ...

// Register a Node-API module:
STDLIB_MATH_BASE_NAPI_MODULE_DDD_D( add );
```

The macro expects the following arguments:

-   **fcn**: `double (*fcn)( double, double, double )` ternary function.

When used, this macro should be used **instead of** `NAPI_MODULE`. The macro includes `NAPI_MODULE`, thus ensuring Node-API module registration.

#### stdlib_math_base_napi_ddd_d( env, info, fcn )

Invokes a ternary function accepting and returning double-precision floating-point numbers.

```c
#include <node_api.h>

// ...

static double add( const double x, const double y, const double z ) {
    return x + y + z;
}

// ...

/**
* Receives JavaScript callback invocation data.
*
* @param env    environment under which the function is invoked
* @param info   callback data
* @return       Node-API value
*/
napi_value addon( napi_env env, napi_callback_info info ) {
    return stdlib_math_base_napi_ddd_d( env, info, add );
}

// ...
```

The function accepts the following arguments:

-   **env**: `[in] napi_env` environment under which the function is invoked.
-   **info**: `[in] napi_callback_info` callback data.
-   **fcn**: `[in] double (*fcn)( double, double, double )` ternary function.

```c
void stdlib_math_base_napi_ddd_d( napi_env env, napi_callback_info info, double (*fcn)( double, double, double ) );
```

#### STDLIB_MATH_BASE_NAPI_MODULE_DII_D( fcn )

Macro for registering a Node-API module exporting an interface for invoking a ternary function accepting a double-precision floating-point number and two signed 32-bit integers and returning a double-precision floating-point number.

```c
#include <stdint.h>

static double fcn( const double x, const int32_t y, const int32_t z ) {
    // ...
}

// ...

// Register a Node-API module:
STDLIB_MATH_BASE_NAPI_MODULE_DII_D( fcn );
```

The macro expects the following arguments:

-   **fcn**: `double (*fcn)( double, int32_t, int32_t )` ternary function.

When used, this macro should be used **instead of** `NAPI_MODULE`. The macro includes `NAPI_MODULE`, thus ensuring Node-API module registration.

#### stdlib_math_base_napi_dii_d( env, info, fcn )

Invokes a ternary function accepting a double-precision floating-point number and two signed 32-bit integers and returning a double-precision floating-point number.

```c
#include <node_api.h>
#include <stdint.h>

// ...

static double fcn( const double x, const int32_t y, const int32_t z ) {
    // ...
}

// ...

/**
* Receives JavaScript callback invocation data.
*
* @param env    environment under which the function is invoked
* @param info   callback data
* @return       Node-API value
*/
napi_value addon( napi_env env, napi_callback_info info ) {
    return stdlib_math_base_napi_dii_d( env, info, fcn );
}

// ...
```

The function accepts the following arguments:

-   **env**: `[in] napi_env` environment under which the function is invoked.
-   **info**: `[in] napi_callback_info` callback data.
-   **fcn**: `[in] double (*fcn)( double, int32_t, int32_t )` ternary function.

```c
void stdlib_math_base_napi_dii_d( napi_env env, napi_callback_info info, double (*fcn)( double, int32_t, int32_t ) );
```

#### STDLIB_MATH_BASE_NAPI_MODULE_FFF_F( fcn )

Macro for registering a Node-API module exporting an interface for invoking a ternary function accepting and returning single-precision floating-point numbers.

```c
static float addf( const float x, const float y, const float z ) {
    return x + y + z;
}

// ...

// Register a Node-API module:
STDLIB_MATH_BASE_NAPI_MODULE_FFF_F( addf );
```

The macro expects the following arguments:

-   **fcn**: `float (*fcn)( float, float, float )` ternary function.

When used, this macro should be used **instead of** `NAPI_MODULE`. The macro includes `NAPI_MODULE`, thus ensuring Node-API module registration.

#### stdlib_math_base_napi_fff_f( env, info, fcn )

Invokes a ternary function accepting and returning single-precision floating-point numbers.

```c
#include <node_api.h>

// ...

static float addf( const float x, const float y, const float z ) {
    return x + y + z;
}

// ...

/**
* Receives JavaScript callback invocation data.
*
* @param env    environment under which the function is invoked
* @param info   callback data
* @return       Node-API value
*/
napi_value addon( napi_env env, napi_callback_info info ) {
    return stdlib_math_base_napi_fff_f( env, info, addf );
}

// ...
```

The function accepts the following arguments:

-   **env**: `[in] napi_env` environment under which the function is invoked.
-   **info**: `[in] napi_callback_info` callback data.
-   **fcn**: `[in] float (*fcn)( float, float, float )` ternary function.

```c
void stdlib_math_base_napi_fff_f( napi_env env, napi_callback_info info, float (*fcn)( float, float, float ) );
```

#### STDLIB_MATH_BASE_NAPI_MODULE_IID_D( fcn )

Macro for registering a Node-API module exporting an interface for invoking a ternary function accepting two signed 32-bit integers and a double-precision floating-point number and returning a double-precision floating-point number.

```c
#include <stdint.h>

static double fcn( const int32_t x, const int32_t y, const double z ) {
    // ...
}

// ...

// Register a Node-API module:
STDLIB_MATH_BASE_NAPI_MODULE_IID_D( fcn );
```

The macro expects the following arguments:

-   **fcn**: `double (*fcn)( int32_t, int32_t, double )` ternary function.

When used, this macro should be used **instead of** `NAPI_MODULE`. The macro includes `NAPI_MODULE`, thus ensuring Node-API module registration.

#### stdlib_math_base_napi_iid_d( env, info, fcn )

Invokes a ternary function accepting two signed 32-bit integers and a double-precision floating-point number and returning a double-precision floating-point number.

```c
#include <node_api.h>
#include <stdint.h>

// ...

static double fcn( const int32_t x, const int32_t y, const double z ) {
    // ...
}

// ...

/**
* Receives JavaScript callback invocation data.
*
* @param env    environment under which the function is invoked
* @param info   callback data
* @return       Node-API value
*/
napi_value addon( napi_env env, napi_callback_info info ) {
    return stdlib_math_base_napi_iid_d( env, info, fcn );
}

// ...
```

The function accepts the following arguments:

-   **env**: `[in] napi_env` environment under which the function is invoked.
-   **info**: `[in] napi_callback_info` callback data.
-   **fcn**: `[in] double (*fcn)( int32_t, int32_t, double )` ternary function.

```c
void stdlib_math_base_napi_iid_d( napi_env env, napi_callback_info info, double (*fcn)( int32_t, int32_t, double ) );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

### Notes

-   The C-API functions expect that the callback `info` argument provides access to the following JavaScript arguments:

    -   `x`: input value.
    -   `y`: input value.
    -   `z`: input value.

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/math-base-napi-ternary.svg
[npm-url]: https://npmjs.org/package/@stdlib/math-base-napi-ternary

[test-image]: https://github.com/stdlib-js/math-base-napi-ternary/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/math-base-napi-ternary/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/math-base-napi-ternary/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/math-base-napi-ternary?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/math-base-napi-ternary.svg
[dependencies-url]: https://david-dm.org/stdlib-js/math-base-napi-ternary/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/math-base-napi-ternary/main/LICENSE

</section>

<!-- /.links -->
