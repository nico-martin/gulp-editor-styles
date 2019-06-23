# Gulp Editor Styles

> Wrap your styles with `.editor-styles-wrapper` to work inside the Gutenberg Block Editor

This is a gulp wrapper for [PostCSS Editor Styles](https://github.com/m-e-h/postcss-editor-styles) by [Marty Helmick](https://martyhelmick.com/)

## Usage
Add **Gulp Editor Styles** to your project:

```bash
npm install gulp-editor-styles --save-dev
```

Use **Gulp Editor Styles** to process your CSS:

```js
// gulpfile.js

const { src, dest, parallel } = require('gulp');
const editorStyles = require('gulp-editor-styles');

function css() {
  return src(YOUR_CSS)
    .pipe(editorStyles(OPTIONS))
    .pipe(minifyCSS())
    .pipe(dest('build/css'))
}
exports.css = css;
```

## Options
These are the options from [PostCSS Editor Styles](https://github.com/m-e-h/postcss-editor-styles/blob/master/README.md#options)

defaults:
```js
const defaults = {
	scopeTo: '.editor-styles-wrapper', // The selector we're working within.
	repeat: 1, // Increase specificity by repeating the selector.
	remove: ['html'],
	replace: ['body'],
	ignore: [':root'],
	tags: ['a', 'button', 'input', 'label', 'select', 'textarea', 'form'],
	tagSuffix: ':not([class^="components-"]):not([class^="editor-"]):not([class^="block-"]):not([aria-owns])'
};
```


