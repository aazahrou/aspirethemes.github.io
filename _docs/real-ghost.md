---
layout: doc
title: Real
categories: docs
platform: Ghost
---

Current Version: 1.1.9 - 15 October 2017

---

* [Theme Installation](#theme-installation)
* [Static Pages](#static-pages)
* [Tags Page](#tags-page)
* [Navigation](#navigation)
* [Search](#search)
* [Disqus Comments](#disqus-comments)
* [Subscribe Form](#subscribe-form)
* [Posts Per Page](#posts-per-page)
* [Google Analytics](#google-analytics)
* [Social Media Links](#social-media-links)
* [Update favicon](#update-favicon)
* [Theme Development](#theme-development)
* [Support](#support)

---

### Theme Installation

* Log into the admin section of your Ghost blog `yourblog.com/ghost`.
* Select `General` from the left-hand side of your admin area and scroll to the bottom **Themes** section.
* Click on the `Upload a Theme` green button.
* An upload box will open, then choose the theme (*real.zip*) within the downloaded package.
* Once uploaded, click on `Activate now` button to activate the theme immediately or `Close` if you want to activate it later.

---

### Static Pages

In order to create a static page, you create a new post, just like you would any other post. Once you have opened up the new post, there is a cog wheel icon next to where it says "Save Draft" or "Update Post" depending on if you have published the post or not. Click on that cog, and check the "Turn this post into a static page" box. This will convert your post to a static page.

![static page](/images/docs/ghost/shared/staticpage.png)

### Navigation

You can add, edit, delete and reorder menu links on your Ghost blog, directly from the navigation tool within the blog admin area, located at **/ghost/settings/navigation/**.

![navigation menu](/images/docs/ghost/shared/navigation-edit.png)

To include a static page on your navigation menu, first, type the name of the page as you'd like it to appear on your menu in the label field.

![label field](/images/docs/ghost/shared/label-field.png)

Next, click on the **URL field** of the menu item. The blog URL will auto-populate with http://yourdomain.com/. You will need to add in the page slug after the final **/**. Once satisfied with your page link, click the blue **Save button** to add the page to the navigation menu.

---

### Search

For the search to work properly, please enable the [Public API Beta](http://support.ghost.org/public-api-beta/).

---

### Tags Page

To enable the tags page:

- Enable the [Public API Beta](http://support.ghost.org/public-api-beta/).
- Create a new post and call it `Tags` for example, and make sure that the POST URL is `tags`.
- Click the `Turn this post into a static page` checkbox.
- Publish the page.
- To add the page to the navigation, please check the [Navigation](#navigation) section above.

![static page](/images/docs/ghost/shared/tags-page.png)

---

### Disqus Comments

The Theme comes with Disqus comments enabled.

Open `partials/disqus.hbs` file, and change the `aspirethemes-demo` value for the `disqus_shortname` variable to match your Disqus account shortname.

```js
var disqus_shortname = "aspirethemes-demo";
```

So, if your Disqus shortname is `exampleone`, the final code above should be

```js
var disqus_shortname = "exampleone";
```

That's all you need to setup Disqus from the theme side. If you get any issue regarding that comments are unable to load. First, make sure you have [registered your website with Disqus (Step 1)](https://help.disqus.com/customer/portal/articles/466182-publisher-quick-start-guide)

And also check [Disqus troubleshooting guide](https://help.disqus.com/customer/portal/articles/472007-i-m-receiving-the-message-%22we-were-unable-to-load-disqus-%22) if you still have issues.

---

### Subscribe Form

Subscribers can be enabled via a checkbox on the Labs page, in your Ghost admin panel:

![enable subscribers](/images/docs/ghost/shared/subscribers-enable.png)

Once you enabled this feature, the form will appear in the single post page.

You can read more about [Subscribers Beta](https://help.ghost.org/hc/en-us/articles/224089787-Subscribers-Beta).

---

### Posts Per Page

With Ghost 1.0, the ["Posts per page"](https://themes.ghost.org/docs/packagejson#section--config-posts_per_page-) setting is now part of the theme. The config purpose is to control how many posts to show per page from the `package.json` file like this:

```js
"config": {
  "posts_per_page": 12
}
```

Aspire theme default value is set to `12` posts per page.

---

### Google Analytics

To integrate Google Analytics, I would recommend reading [Google Analytics](https://help.ghost.org/hc/en-us/articles/115000450512-Google-Analytics) integration steps by Ghost.

---

### Social Media Links

Social media links are placed in:

* `partials/footer.hbs`

The theme is using [Evil Icons](http://evil-icons.io/), which contains very simple and clean icons. Here you can find a list of the social media icons to use:

{% include evil-icons.liquid %}

---

### Update favicon

You can find the current favicon inside the theme **assets** directory, just replace it with your new favicon, then upload to the server.

![Update favicon](/images/docs/ghost/shared/update-favicon.png)

---

### Theme Development

If you are a developer and need to do customization work, the theme is using [Gulp](https://github.com/gulpjs/gulp) to compile [Sass](http://sass-lang.com/) and JavaScript. This improves the development flow and making it much faster.

First, make sure you have [Node.js](https://nodejs.org/en/), [npm](https://www.npmjs.com/), and [Bower](https://bower.io/#install-bower) installed, then run the-the following commands in the theme root directory to install *npm* and *bower* dependencies.

```sh
npm install
```

To start Gulp, run:

```sh
gulp
```

This will compile Sass and JavaScript files, and start watching changes as you edit files.

---

### Support

If you have any questions, I'd be happy to help.

* Email: [aspirethemes@gmail.com](mailto:aspirethemes@gmail.com)
* Twitter: [@aspirethemes](https://twitter.com/aspirethemes)

---