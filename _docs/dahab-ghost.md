---
layout: doc
status: review
title: Dahab
categories: docs
platform: Ghost
---

Current Version: In review

---

* [Theme Installation](#theme-installation)
* [Static Pages](#static-pages)
* [Navigation](#navigation)
* [Home Hero](#home-hero)
* [Tags Page](#tags-page)
* [Disqus Comments](#disqus-comments)
* [Subscribe Form](#subscribe-form)
* [Posts Per Page](#posts-per-page)
* [Google Analytics](#google-analytics)
* [Social Media Links](#social-media-links)
* [Update Favicon](#update-favicon)
* [Theme Development](#theme-development)
* [Support](#support)

---

### Theme Installation

This is a quick video showing how to install the theme, upload blog cover image, favicon, social media account, create the tags page, and update the profile information for the editor.

<iframe src="https://www.youtube.com/embed/wqtI7QwCWNc" frameborder="0" allowfullscreen></iframe>

---

Also, you can follow the follwing steps to install the theme:

* Log into the admin section of your Ghost blog `yourblog.com/ghost`.
* Select `Design` from the left hand side of your admin area and go to the **Themes** section.
* Click on the `Upload a Theme` green button.
* An upload box will open, then choose the theme (*dahab.zip*) within the downloaded package.
* Once uploaded, click on `Activate now` button to activate the theme immediately or `Close` if you want to activate it later.

---

### Static Pages

In order to create a static page you create a new post, just like you would any other post. Once you have opened up the new post, there is a cog wheel icon next to where it says "Save Draft" or "Update Post" depending on if you have published the post or not. Click on that cog, and check the "Turn this post into a static page" box. This will convert your post to a static page.

![static page](/images/docs/ghost/dahab/static-page.png)

---

### Navigation

You can add, edit, delete and reorder menu links on your Ghost blog, directly from the navigation tool within the blog admin area, located at **/ghost/#/settings/design/**.

![navigation menu](/images/docs/ghost/dahab/navigation-edit.png)

To include a static page on your navigation menu, first, type the name of the page as you'd like it to appear on your menu in the label field.

![label field](/images/docs/ghost/dahab/label-field.png)

Next, click inside the **URL field** of the menu item. The blog URL will auto-populate with http://yourdomain.com/. You will need to add in the page slug after the final **/**. Once satisfied with your page link, click the blue **Save button** to add the page to the navigation menu.

---

### Home Hero

![static page](/images/docs/ghost/dahab/home-hero.jpg)

The hero section shows the cover image and the blog description, which you can edit from the [Blog Settings](https://help.ghost.org/hc/en-us/articles/223207167-Blog-Settings-Overview) admin page.

The theme comes with description support for HTML tags, so you can add normal tags like custom links or headings and the theme will automatically render them on the browser. For example, the demo description is the following:

{% highlight html %}
<h3>Thoughts, Stories and Ideas.</h3>
{% endhighlight %}

---

### Tags Page

![tags page](/images/docs/ghost/dahab/tags-page.jpg)

To enable the tags page:

- Enable the [Public API Beta](http://support.ghost.org/public-api-beta/).
- Create a new post and call it `Tags` for example, and make sure that the POST URl is `tags`.
- Click the `Turn this post into a static page` checkbox.
- Publish the page.
- To add the page to the navigation, please check the [Navigation](#navigation) section above.

![static page](/images/docs/ghost/dahab/tags-page.png)

---

### Disqus Comments

The Theme comes with Disqus comments enabled.

Open `partials/disqus.hbs` file, and change the `aspirethemes-demos` value for the `disqus_shortname` variable to match your Disqus account shortname.

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

![enable subscribers](/images/docs/ghost/dahab/subscribers-enable.png)

Once you enabled this feature, the form will appear in the single post page.

You can read more about [Subscribers](http://support.ghost.org/subscribers-beta/)

---

### Posts Per Page

With Ghost 1.0, the ["Posts per page"](https://themes.ghost.org/docs/packagejson#section--config-posts_per_page-) setting is now part of the theme. The config purpose is to control how many posts to show per page from the `package.json` file like this:

```js
"config": {
  "posts_per_page": 6
}
```

Dahab theme default value is set to `6` posts per page.

---

### Google Analytics

To integrate Google Analytics, I would recommend reading [How do I add Google Analytics to my blog?](http://support.ghost.org/add-google-analytics-blog/) by Ghost.

---

### Social Media Links

Ghost supports adding Facebook and Twitter profile URLs from the admin panel, go to **General > Social accounts** and add your URLs, and this will update the Facebook and Twitter URLs in the blog footer.

![social-accounts](/images/docs/ghost/dahab/social-accounts.png)

If you want to add more static social media links, you can open directly add them in: `partials/social-nav.hbs` file.

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

Google-plus

{% highlight html %}
<span data-icon="ei-sc-google-plus" data-size="s"></span>
{% endhighlight %}

Soundcloud

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

### Update Favicon

#### New Ghost 1.0

The favicon in Ghost 1.0 could be changed from the [Blog settings](https://help.ghost.org/hc/en-us/articles/223207167-Blog-Settings-Overview) from the Publication icon section.

![Update favicon](/images/docs/ghost/shared/update-favicon-ghost-1.png)

#### Old Ghost Versions

You can find the current favicon inside the theme **assets** directory, just replace it with your new favicon, then upload to the server.

![Update favicon](/images/docs/ghost/shared/update-favicon.png)

---

### Theme Development

If you are a developer and need to do customization work, the theme is using [Gulp](https://github.com/gulpjs/gulp) to compile [Sass](http://sass-lang.com/) and JavaScript. This improves the development flow and making it much faster.

First, make sure you have [Node.js](https://nodejs.org/en/), [npm](https://www.npmjs.com/), and [Bower](https://bower.io/#install-bower) installed, then run the-the following commands in the theme root directory to install *npm* and *bower* dependencies.

{% highlight shell %}
yarn install
{% endhighlight %}

To start Gulp, run:

{% highlight shell %}
gulp
{% endhighlight %}

This will compile Sass and JavaScript files, and start watching changes as you edit files.

---

To create a clean and small theme package, you can exclude different directories using the following command line:

{% highlight shell %}
zip -r dahab.zip dahab -x *node_modules* *bower_components* *git*
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