---
layout: post
title: Add Rtl Support to WordPress Theme With Sass and Gulp
tags: [RTL, Gulp, Sass, CSS, WordPress]
image: '/images/posts/wordpress-rtl-with-gulp/thumbnail.png'
---

At Aspire Themes, I always care and provide RTl CSS support for all WordPress themes, this helps many customers and website owners to provide and support more languages like Arabic or Hebrew, or any language that you can read from right to left (RTL).

I use Gulp as a JavaScript task runner to automate everything in theme development, things like Sass compilation, CSS auto-prefix, JavaScript validation, browser refresh, ... and In this post, I will use [gulp-rtlcss](https://www.npmjs.com/package/gulp-rtlcss) and [gulp-rename](https://www.npmjs.com/package/gulp-rename) plugins to generate the RTL CSS file (rtl.css).

I assume you have some experience with [Gulp](http://gulpjs.com/), [Node.js](https://nodejs.org/en/) is installed in your system and have WordPress installed and configured.

I will use the [underscore](http://underscores.me/) as the base theme. You can download it and activate from the dashboard.

Then, navigate to the theme directory using the command line, like:

{% highlight shell %}
cd ~/www/wordpress/wp-content/themes/wordpress-rtl-with-gulp
{% endhighlight %}

While you are in the theme directory, run the `npm init` command and follow a few simple steps to create a `package.json` file which will include some information about the theme and the packages that will be installed.

An example of `package.json` that you will get after finishing up the steps.

{% highlight js %}
{
  "name": "Wordpress RTL with Gulp",
  "version": "1.0.0",
  "description": "Add RTL Support to WordPress Theme with Sass and Gulp",
  "author": "Aspire Themes"
}
{% endhighlight %}

Install the required Gulp plugins:

{% highlight shell %}
npm install gulp gulp-sass gulp-rtlcss gulp-rename --save-dev
{% endhighlight %}

Next,  create a Sass directory with a basic structure

{% highlight shell %}
├── sass
│   └── style.scss
{% endhighlight %}

The `style.scss` is the main starting point file, which will include all your components, modules, functions inside it based on your preference.  You can copy the content of `style.css` file into `style.scss` or you can create your own styles, and in this case, `style.css` will be overwritten by your new styles.

{% highlight css %}
/*
  Theme Name: Aspire
  Theme URI: http://aspirethemes.com
  Author: Aspire Themes
  Author URI: http://aspirethemes.com
  Description: Add RTL Support to WordPress Theme with Sass and Gulp
  Version: 1.0.0
  License:
  License URI:
  Text Domain: aspire
*/

body {
  text-align: left;
  direction: ltr;
}

.column { float: left; }
{% endhighlight %}

The next step is to create a `gulpfile.js` file and include the newly installed plugins and add the `sass` task.

{% highlight js %}
var gulp    = require('gulp'),
    sass    = require('gulp-sass'),
    rtlcss  = require('gulp-rtlcss'),
    rename  = require('gulp-rename');

gulp.task('sass', function() {
  return gulp.src('./sass/*.scss')
  .pipe(sass())
  .pipe(gulp.dest('./'))  // Output LTR (style.css)

  .pipe(rtlcss())                     // Convert to RTL
  .pipe(rename({ basename: 'rtl' }))  // Rename to rtl.css
  .pipe(gulp.dest('./'));             // Output RTL (rtl.css)
});
{% endhighlight %}

The idea behind `gulp-rtlcss` is to convert all the CSS properties like floats, text-align, text direction, and other properties from left to right.

The second plugin is [`gulp-rename`](https://www.npmjs.com/package/gulp-rename) which will rename the file to `rtl.css` automatically.

In this step, the plugin will convert all the CSS properties like floats and text direction from left to right, then rename the file to `rtl.css`, and then output the file to the theme root.

Now, run `gulp` from the command line.

![gulp-rtl-command](/images/posts/wordpress-rtl-with-gulp/gulp-rtl.png)

This will generate `style.css`

{% highlight css %}
/*
  Theme Name: Aspire
  Theme URI: http://aspirethemes.com
  Author: Aspire Themes
  Author URI: http://aspirethemes.com
  Description: Add RTL Support to WordPress Theme with Sass and Gulp
  Version: 1.0.0
  License:
  License URI:
  Text Domain: aspire
*/
body {
  text-align: left;
  direction: ltr; }

.column {
  float: left; }
{% endhighlight %}

and `rtl.css` files.

{% highlight css %}
/*
  Theme Name: Aspire
  Theme URI: http://aspirethemes.com
  Author: Aspire Themes
  Author URI: http://aspirethemes.com
  Description: Add RTL Support to WordPress Theme with Sass and Gulp
  Version: 1.0.0
  License:
  License URI:
  Text Domain: aspire
*/
body {
  text-align: right;
  direction: rtl; }

.column {
  float: right; }
{% endhighlight %}

Notice that, `left` becomes `right`, and direction `ltr` becomes `rtl` automatically.

I’ve created a GitHub repo for this article’s WordPress theme and [you can check out the code here](https://github.com/aspirethemes/wordpress-rtl-with-gulp).

You can check the WordPress theme for this article on [Github](https://github.com/aspirethemes/wordpress-rtl-with-gulp).

## Conclusion

Gulp makes the development process much easier than before, not only compiling Sass to CSS, or generating the RTL file, but for many other tasks like CSS auto-prefixing, JavaScript validation, watching files and much more, and I highly recommend to add it to your development arsenal.

Have you tried to work and generate WordPress `rtl.css` file before, what was your experience? If you use Gulp in your development workflow, which plugins do you use regularly and recommend?