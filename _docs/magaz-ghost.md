---
layout: doc
title: Magaz
categories: docs
platform: Ghost
---

Current Version: 1.2.0 - 7 August 2017

---

* [Theme Installation](#theme-installation)
* [Static Pages](#static-pages)
* [Navigation](#navigation)
* [Search](#search)
* [Disqus Comments](#disqus-comments)
* [Subscribe Form](#subscribe-form)
* [Posts Per Page](#posts-per-page)
* [Google Analytics](#google-analytics)
* [Related Posts](#relatedposts)
* [Social Media Links](#social-media-links)
* [Update Favicon](#update-favicon)
* [Copyright Information](#copyright-information)
* [Theme Development](#theme-development)
* [Support](#support)

---

### Theme Installation

* Log into the admin section of your Ghost blog `yourblog.com/ghost`.
* Select `General` from the left hand side of your admin area and scroll to the bottom **Themes** section.
* Click on the `Upload a Theme` green button.
* An upload box will open, then choose the theme (*magaz.zip*) within the downloaded package.
* Once uploaded, click on `Activate now` button to activate the theme immediately or `Close` if you want to activate it later.

---

### Static Pages

In order to create a static page you create a new post, just like you would any other post. Once you have opened up the new post, there is a cog wheel icon next to where it says "Save Draft" or "Update Post" depending on if you have published the post or not. Click on that cog, and check the "Turn this post into a static page" box. This will convert your post to a static page.

![static page](/images/docs/ghost/shared/staticpage.png)

---

### Navigation

You can add, edit, delete and reorder menu links on your Ghost blog, directly from the navigation tool within the blog admin area, located at **/ghost/settings/navigation/**.

![navigation menu](/images/docs/ghost/shared/navigation-edit.png)

To include a static page on your navigation menu, first, type the name of the page as you'd like it to appear on your menu in the label field.

![label field](/images/docs/ghost/shared/label-field.png)

Next, click inside the **URL field** of the menu item. The blog URL will auto-populate with http://yourdomain.com/. You will need to add in the page slug after the final **/**. Once satisfied with your page link, click the blue **Save button** to add the page to the navigation menu.

---

### Search

For the search to work properly, please enable the [Public API Beta](http://support.ghost.org/public-api-beta/).

---

### Disqus Comments

Magaz Theme comes with Disqus comments enabled.

Open `partials/disqus.hbs` file, and change the `aspirethemes-demo` value for the `disqus_shortname` variable to match your Disqus account shortname.

{% highlight js %}
var disqus_shortname = "aspirethemes-demos";
{% endhighlight %}

So, if your Disqus shortname is `exampleone`, the final code above should be

{% highlight js %}
var disqus_shortname = "exampleone";
{% endhighlight %}

That's all you need to setup Disqus from the theme side. If you get any issue regarding that comments are unable to load. First, make sure you have [registered your website with Disqus (Step 1)](https://help.disqus.com/customer/portal/articles/466182-publisher-quick-start-guide)

And also check [Disqus troubleshooting guide](https://help.disqus.com/customer/portal/articles/472007-i-m-receiving-the-message-%22we-were-unable-to-load-disqus-%22) if you still have issues.

---

### Subscribe Form

Subscribers can be enabled via a checkbox on the Labs page, in your Ghost admin panel:

![enable subscribers](/images/docs/ghost/shared/subscribers-enable.png)

Once you enabled this feature, the form will appear in two places:

* Footer
* Single post page sidebar widget

You can read more about [Subscribers](http://support.ghost.org/subscribers-beta/)

---

### Posts Per Page

With Ghost 1.0, the ["Posts per page"](https://themes.ghost.org/docs/packagejson#section--config-posts_per_page-) setting is now part of the theme. The config purpose is to control how many posts to show per page from the `package.json` file like this:

```js
"config": {
  "posts_per_page": 15
}
```

Magaz theme default value is set to `15` posts per page.

---

### Google Analytics

To integrate Google Analytics, I would recommend reading [How do I add Google Analytics to my blog?](http://support.ghost.org/add-google-analytics-blog/) by Ghost.

---

### RelatedPosts

Related posts will be visible on the single post page when there are similar posts with similar tags, and will be hidden otherwise.

You will need to enable the Public Api from Ghost admin. Go to `Settings > Labs` and check the *Public Api* mark to enable it.

![enable-public-api](/images/docs/ghost/shared/enable-public-api.png)

---

### Social Media Links

Ghost supports adding Facebook and Twitter profile URLs from the admin panel, go to **General > Social accounts** and add your URLs, and this will update the Facebook and Twitter URLs in the blog footer.

![social-accounts](/images/docs/ghost/dahab/social-accounts.png)

Social media links are placed in different places (files):

* `partials/header.hbs`
* `partials/footer.hbs`

The theme is using [Evil Icons](http://evil-icons.io/), which contains very simple and clean icons. Here you can find a list of the social media icons to use:

Twitter

{% highlight html %}
<span data-icon="ei-sc-twitter" data-size="s"></span>
{% endhighlight %}

Facebook

{% highlight html %}
<span data-icon="ei-sc-facebook" data-size="s"></span>
{% endhighlight %}

Instagram

{% highlight html %}
<span data-icon="ei-sc-instagram" data-size="s"></span>
{% endhighlight %}

Pinterest

{% highlight html %}
<span data-icon="ei-sc-pinterest" data-size="s"></span>
{% endhighlight %}

Vimeo

{% highlight html %}
<span data-icon="ei-sc-vimeo" data-size="s"></span>
{% endhighlight %}

Google Plus

{% highlight html %}
<span data-icon="ei-sc-google-plus" data-size="s"></span>
{% endhighlight %}

SoundCloud

{% highlight html %}
<span data-icon="ei-sc-soundcloud" data-size="s"></span>
{% endhighlight %}

Tumblr

{% highlight html %}
<span data-icon="ei-sc-tumblr" data-size="s"></span>
{% endhighlight %}

Youtube

{% highlight html %}
<span data-icon="ei-sc-youtube" data-size="s"></span>
{% endhighlight %}

---

### Update favicon

#### New Ghost 1.0

The favicon in Ghost 1.0 could be changed from the [Blog settings](https://help.ghost.org/hc/en-us/articles/223207167-Blog-Settings-Overview) from the Publication icon section.

![Update favicon](/images/docs/ghost/shared/update-favicon-ghost-1.png)

#### Old Ghost Versions

You can find the current favicon inside the theme **assets** directory, just replace it with your new favicon, then upload to the server.

![Update favicon](/images/docs/ghost/shared/update-favicon.png)

---

### Copyright Information

You will find copyright information at the bottom of `partials/footer.hbs` file.

---

### Theme Development

If you are a developer and need to do customization work, the theme is using [Gulp](https://github.com/gulpjs/gulp) to compile [Sass](http://sass-lang.com/) and JavaScript. This improves the development flow and making it much faster.

First, make sure you have [Node.js](https://nodejs.org/en/), [npm](https://www.npmjs.com/), and [Bower](https://bower.io/#install-bower) installed, then run the-the following commands in the theme root directory to install *npm* and *bower* dependencies.

{% highlight shell %}
npm install
{% endhighlight %}

To start Gulp, run:

{% highlight shell %}
gulp
{% endhighlight %}

This will compile Sass and JavaScript files, and start watching changes as you edit files.

---

To create a clean and small theme package, you can exclude different directories using the following command line:

{% highlight shell %}
zip -r magaz.zip magaz -x *node_modules* *bower_components* *git*
{% endhighlight %}

This will exclude *node_modules*, *bower_components*, and *git* directories from the final zip file.

---

Another option is to use the Ghost [Code Injection](https://help.ghost.org/hc/en-us/articles/223403488-Code-Injection) feature. This is great if you don’t want to touch the theme files which is recommended to receive the future theme updates without losing your customizations.

---

### Support

If you have any questions, I'd be happy to help.

* _Email:_ [aspirethemes@gmail.com](mailto:aspirethemes@gmail.com)
* _Twitter:_ [@aspirethemes](https://twitter.com/aspirethemes)

---