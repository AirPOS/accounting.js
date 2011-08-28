**accounting.js** is a tiny JavaScript library for number, money and currency formatting, with optional excel-style column rendering (to line up symbols and decimals). It's lightweight, fully localisable and has zero dependencies.

Check out the plugin homepage (with demos and docs) here: **http://josscrowcroft.github.com/accounting.js/**

## To do for v0.2
* Write tests and update docs/demos for enhanced formatting options
* Do some optimisations for performance bottlenecks

## Changelog

### v0.2
* Compleat (non-breaking) rewrite of the formatting system for **formatMoney** and **formatColumn**, to allow more fine-grained control of string output, still easy as pie
* Separate formats for negative and zero values now supported (optionally) via `accounting.settings.currency.format`
* Added `isArray`, `isString` and `isObject` helper methods from underscore.js for readability/maintainability

### v0.1.5
* Added `map()` helper method based on underscore.js's `_.map()`, for array iteration, falls back to native `Array.map` if available.

### v0.1.4
* Added helper method `defaults` to extend an object's empty properties with a defaults object
* API methods now use **defaults()** to give more structure to the second-parameter-object method style: parameters are normalised into an `opts` object inside each method
* Settings object at top of library for readibility
* **formatMoney** now recursively formats arrays
* Added Jasmine test suite (thx [millermedeiros](https://github.com/millermedeiros)!) and QUnit functionality + speed tests

### v0.1.3
* Refactored library codebase to use a configurable settings object for default formatting parameters, which paves the way for plugins later on.
* Added `format` parameter to control symbol and value position (default `"%s%v"`, or [symbol][value])
* Made methods more consistent in accepting an object as 2nd parameter, matching/overriding the library defaults

### v0.1.2
* **formatColumn** now works recursively on nested arrays, eg `accounting.formatColumn( [[1,12,123,1234], [1234,123,12,1]] )`, returning back a matching array with inner columns lined up
* Another fix for rounding in **formatNumber**: `54324.535` now rounds to ".54" instead of ".53"

### v0.1.1
* Added **toFixed** method (`accounting.toFixed(value, precision)`), which treats floats more like decimals for more accurate currency rounding - now, `0.615` rounds up to `$0.62` instead of `$0.61`
* Minified version now preserves semicolons
* Fixed NaN errors when no value in **unformat** - revisit later on