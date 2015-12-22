## gulp-lazyimagecss
[![NPM Version](http://img.shields.io/npm/v/gulp-lazyimagecss.svg?style=flat)](https://www.npmjs.com/package/gulp-lazyimagecss) 
[![NPM Downloads](https://img.shields.io/npm/dm/gulp-lazyimagecss.svg?style=flat)](https://www.npmjs.com/package/gulp-lazyimagecss) 
[![License](https://img.shields.io/npm/l/gulp-lazyimagecss.svg?style=flat)](http://opensource.org/licenses/MIT) 

> Be lazy, add images's CSS automatically, like `width` & `height` and more.    
> Save time, make money.

**NPM Home Page:** [https://www.npmjs.com/package/gulp-lazyimagecss](https://www.npmjs.com/package/gulp-lazyimagecss)

## Install

Install with [NPM](https://npmjs.org/):

```javascript
npm install gulp-lazyimagecss --save
```

## Usage

**gulpfile.js**

```javascript
var lazyimagecss = require('gulp-lazyimagecss');

gulp.src(paths.src.less)
    .pipe(less())
    .pipe(lazyimagecss())
    .pipe(gulp.dest(paths.src.css));
        	
```

**Options**  
Set CSS which you wish to be added automatically.

```javascript
options = lodash.extend({
    width: true,
    height: true,
    backgroundSize: true, 
    slice: '../slice' // Set slice image path
}, options);
```

## Result

**CSS In**


```css
.icon-test {
	background-image: url(../slice/test.png);
}
```

**CSS Out**

```css
.icon-test {
	width: 32px;
	height: 66px;
	background-image: url(../slice/test.png);
	background-size: 32px;
}
```

_Tips: Use [PostCSS](https://github.com/postcss/postcss) with the `CSS Out` if needed._

## Notes

* Get image size from `HEX` data from file buffer via [fast-image-size](https://github.com/Ziv-Barber/fast-image-size), more fast now.
* Detect `PNG` & `JPG` based on [file signatures](https://en.wikipedia.org/wiki/List_of_file_signatures)

## Team

[TmT Team](https://github.com/orgs/TmT/people)