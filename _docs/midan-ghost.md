---
layout: doc
title: Midan
categories: docs
platform: Ghost
---

Current Version: 1.1.6 - 11 Sept 2017

---

* [Theme Installation](#theme-installation)
* [Static Pages](#static-pages)
* [Navigation](#navigation)
* [Disqus Comments](#disqus-comments)
* [Google Analytics](#google-analytics)
* [Social Media Links](#social-media-links)
* [Update favicon](#update-favicon)
* [Copyright Information](#copyright-information)
* [Theme Development](#theme-development)
* [Support](#support)

---

### Theme Installation

* Log into the admin section of your Ghost blog `yourblog.com/ghost`.
* Select `Design` from the left hand side of your admin area and go to the **Themes** section.
* Click on the `Upload a Theme` green button.
* An upload box will open, then choose the theme (*midan.zip*) within the downloaded package.
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

### Disqus Comments

The Theme comes with Disqus comments enabled.

Open `partials/disqus.hbs` file, and change the `aspirethemes-demo` value for the `disqus_shortname` variable to match your Disqus account shortname.

{% highlight js %}
var disqus_shortname = "aspirethemes-demo";
{% endhighlight %}

So, if your Disqus shortname is `exampleone`, the final code above should be

{% highlight js %}
var disqus_shortname = "exampleone";
{% endhighlight %}

That's all you need to setup Disqus from the theme side. If you get any issue regarding that comments are unable to load. First, make sure you have [registered your website with Disqus (Step 1)](https://help.disqus.com/customer/portal/articles/466182-publisher-quick-start-guide)

And also check [Disqus troubleshooting guide](https://help.disqus.com/customer/portal/articles/472007-i-m-receiving-the-message-%22we-were-unable-to-load-disqus-%22) if you still have issues.

---

### Google Analytics

To integrate Google Analytics, I would recommend reading [How do I add Google Analytics to my blog?](http://support.ghost.org/add-google-analytics-blog/) by Ghost.

---

### Social Media Links

Social media links are placed in:

* `partials/footer.hbs`

Ghost 0.8.0 supports adding Facebook and Twitter profile urls from the admin panel, go to **Settings > General** and add your URLs, and this will update the Facebook and Twitter URLs in the location mentioned above, other social media URLs you can add it from the file.

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

### Support

If you have any questions, I'd be happy to help.

* _Email:_ [aspirethemes@gmail.com](mailto:aspirethemes@gmail.com)
* _Twitter:_ [@aspirethemes](https://twitter.com/aspirethemes)

---