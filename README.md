# gulp-concat-mutli

A wrapper around [gulp-concat](https://github.com/contra/gulp-concat) that allows you to define multiple sets of files, which each combine into their own unique file.

## Installation

You know how we do.

```bash
npm install gulp-concat-multi --save
```

## Usage

gulp-multi-concat is used in place of `gulp.src()`. It concatenates your sets of files and then returns a stream of the combined files for you to mess with further.

```js
var concat = require('gulp-multi-concat');

function scripts() {
  concat({
    'vendor.js': 'js/vendor/**/*.js',
    'app.js': ['js/lib/**/*.js', 'js/app.js']
  })
    .pipe(uglify())
    .pipe(gulp.dest('dist/js'));
}
```

No source map support at the moment.
