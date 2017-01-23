### Overview calling stack

We start by loading `index.html` from the browser ->
- Line 8 in `index.html` will then load `run_prettify.js`

#### run_prettify.js

- We enter the scope function at line 115 in `run_prettify.js`
- we reach line 276 in `run_prettify.js` which calls

  `loadStylesheetsFallingBack(skinUrls)`

This function will load the following style sheet:
https://cdn.rawgit.com/google/code-prettify/master/loader/prettify.css

I created a local copy of the file at [`private/css/prettify.css`](https://github.com/hakonhagland/code-prettify/blob/perl_fix/private/css/prettify.css)

- On line 278 variable `prettyPrint` is defined by calling an anonymous
  scope function that extends all the way to line 1968.

- A new scope function is entered a line 393 of `run_prettify.js`
  which extends to line 1966

- A function `combinePrefixPatterns()` is defined at line 550 which
  extends to line 781.

- A function `extractSourceSpans()` is defined at line 828, and it
  extends to line 872.

