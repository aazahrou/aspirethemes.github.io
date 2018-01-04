---
layout: doc
title: Nubia
categories: docs
platform: Ghost
---

Current Version: 1.0.1 - 24 December 2017

---

* [Theme Installation](#theme-installation)
* [Enable the Public API](#enable-the-public-api)
* [Static Pages](#static-pages)
* [Navigation](#navigation)
* [Search](#search)
* [Tags Page](#tags-page)
* [Authors Page](#authors-page)
* [Contact Page](#contact-page)
* [Disqus Comments](#disqus-comments)
* [Instagram](#instagram)
* [Posts Per Page](#posts-per-page)
* [Related Posts](#related-posts)
* [Google Analytics](#google-analytics)
* [Subscribe Form](#subscribe-form)
* [Social Media Links](#social-media-links)
* [Update Favicon](#update-favicon)
* [Theme Development](#theme-development)
* [Support](#support)

---

### Theme Installation

* Log into the admin section of your Ghost blog `yourblog.com/ghost`.
* Select `Design` from the left hand side of your admin area and go to the **Themes** section.
* Click on the `Upload a Theme` green button.
* An upload box will open, then choose the theme (*nubia.zip*) within the downloaded package.
* Once uploaded, click on `Activate now` button to activate the theme immediately or `Close` if you want to activate it later.

---

### Enable the Public API

Public API is important for some functionality like search, tags page, and subscribe form to work properly. You can enable the Public API from Ghost admin. Go to `Labs > Beta features` section and check the *Public API* mark to enable it.

![enable-public-api](/images/docs/ghost/shared/beta-features.png)

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

For the search to work properly, please make sure that the [Public API](#enable-the-public-api) is enabled.

---

### Tags Page

To create the tags page:

- Enable the [Public API](#enable-the-public-api).
- Create a new post and call it `Tags` for example, and make sure that the POST URl is `tags`.
- Click the `Turn this post into a static page` checkbox.
- Publish the page.
- To add the page to the navigation, please check the [Navigation](#navigation) section above.

![static page](/images/docs/ghost/shared/tags-page.png)

---

### Authors Page

To create the Authors page:

- Enable the [Public API](#enable-the-public-api).
- Create a new post and call it `Authors` for example, and make sure that the POST URl is `authors`.
- Click the `Turn this post into a static page` checkbox.
- Publish the page.
- To add the page to the navigation, please check the [Navigation](#navigation) section above.

![static page](/images/docs/ghost/nubia/authors-page.png)

---

### Contact Page

To create the Contact page:

- Create a new post and call it `Contact` for example.
- Add your content and the contact form code using [FORMSPREE](https://formspree.io/) as a service. Please check the  code example below.
- Click the `Turn this post into a static page` checkbox.
- Publish the page.
- To add the page to the navigation, please check the [Navigation](#navigation) section above.

```html
<form action="https://formspree.io/your@email.com" method="POST">
  <input type="text" name="name" placeholder="Name">
  <input type="email" name="_replyto" placeholder="Email">
  <textarea name='message' placeholder="Message"></textarea>
  <input class='c-btn c-btn--small c-btn--active' type="submit" value="Send">
</form>
```

For more information, check the [How to Add a Contact Form to Your Ghost Blog](https://aspirethemes.com/blog/ghost-contact-form) blog post.

---

### Disqus Comments

Nubia Theme comes with Disqus comments enabled.

Open `partials/disqus.hbs` file, and change the `aspirethemes-demos` value for the `disqus_shortname` variable to match your Disqus account shortname.

```js
var disqus_shortname = 'aspirethemes-demos';
```

So, if your Disqus shortname is `exampleone`, the final code above should be:

```js
var disqus_shortname = 'exampleone';
```

That's all you need to setup Disqus from the theme side. If you get any issue regarding that comments are unable to load. First, make sure you have [registered your website with Disqus (Step 1)](https://help.disqus.com/customer/portal/articles/466182-publisher-quick-start-guide)

And also check [Disqus troubleshooting guide](https://help.disqus.com/customer/portal/articles/472007-i-m-receiving-the-message-%22we-were-unable-to-load-disqus-%22) if you still have issues.

---

### Instagram

The Instagram feed is working using [Instafeed.js](http://instafeedjs.com/) to show the photos.

First, you will need to get your account `userId` and `accessToken` from the following URLs:

- userId: [smashballoon.com/instagram-feed/find-instagram-user-id](https://smashballoon.com/instagram-feed/find-instagram-user-id/)
- accessToken: [instagram.pixelunion.net](http://instagram.pixelunion.net/)

Second, open the `assets/js/instagram.js` file and replace the `userId` and `accessToken` values.

```js
var instagramFeed = new Instafeed({
  get: 'user',
  limit: 6,
  resolution: 'thumbnail',
  userId: '',
  accessToken: ''
});
```

You can control how much images to show by changing the `limit` number. Theme default is set to `6` images.

---

### Posts Per Page

With Ghost 1.0, the [Posts per page](https://themes.ghost.org/docs/packagejson#section--config-posts_per_page-) setting is now part of the theme. The config purpose is to control how many posts to show per page from the `package.json` file like this:

```js
"config": {
  "posts_per_page": 11
}
```

Nubia theme default value is set to `11` posts per page.

---

### Related Posts

Related posts will be visible on the single post page when there are similar posts with similar tags, and will be hidden otherwise.

Enabling the [Public API](#enable-the-public-api) is required.

---

### Google Analytics

To integrate Google Analytics, I would recommend reading [Google Analytics](https://help.ghost.org/hc/en-us/articles/115000450512-Google-Analytics) integration steps by Ghost.

---

### Subscribe Form

Subscribers can be enabled via a checkbox on the Labs page (`Labs > Beta features`), in your Ghost admin panel:

![enable subscribers](/images/docs/ghost/shared/beta-features.png)

Once you enabled this feature, the form will appear in the footer.

You can read more about [Subscribers Beta](https://help.ghost.org/hc/en-us/articles/224089787-Subscribers-Beta).

---

### Social Media Links

Social media links are placed in the `partials/social-icons.hbs` file.

Ghost supports adding Facebook and Twitter profile URLs from the admin panel, go to **General > Social accounts** and add your URLs, this will update the Facebook and Twitter URLs within the footer social media section.

![social-accounts](/images/docs/ghost/shared/social-accounts.png)

For using other social accounts, the theme is using [Evil Icons](http://evil-icons.io/), which contains very simple and clean icons. Here you can find a list of the social media icons to use:

Twitter

```html
<span data-icon='ei-sc-twitter' data-size='s'></span>
```

Facebook

```html
<span data-icon='ei-sc-facebook' data-size='s'></span>
```

Instagram

```html
<span data-icon='ei-sc-instagram' data-size='s'></span>
```

Pinterest

```html
<span data-icon='ei-sc-pinterest' data-size='s'></span>
```

Vimeo

```html
<span data-icon='ei-sc-vimeo' data-size='s'></span>
```

Google Plus

```html
<span data-icon='ei-sc-google-plus' data-size='s'></span>
```

SoundCloud

```html
<span data-icon='ei-sc-soundcloud' data-size='s'></span>
```

Tumblr

```html
<span data-icon='ei-sc-tumblr' data-size='s'></span>
```

Youtube

```html
<span data-icon='ei-sc-youtube' data-size='s'></span>
```

To edit or update other excisted and static social links, for exmaple, the Instagram code block:

```html
<li class='c-social-icons__item'>
  <a href='#' aria-label='Instagram' target='_blank' rel='noopener'>
    <span class='c-social-icons__icon' data-icon='ei-sc-instagram' data-size='s'></span>
  </a>
</li>
```

The code above contains the ICON code from the above list, the social media link (`a`) within a list element (`li`).

Next, replace your Instagram full URL with the link `href` value so if your Instagram URL is:

```html
https://www.instagram.com/ghost/
```

the new code will be:

```html
<li class='c-social-icons__item'>
  <a href='https://www.instagram.com/ghost/' aria-label='Instagram' target='_blank' rel='noopener'>
    <span class='c-social-icons__icon' data-icon='ei-sc-instagram' data-size='s'></span>
  </a>
</li>
```

If you want to completly remove Instagram, you can delete all the code block, the `li`, `a`, and the icon.

---

### Update Favicon

The favicon in Ghost 1.0 could be changed from the [Blog settings](https://help.ghost.org/hc/en-us/articles/223207167-Blog-Settings-Overview) from the Publication icon section.

![Update favicon](/images/docs/ghost/shared/update-favicon-ghost-1.png)

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

To create a clean and small theme package, you can exclude different directories using the following command line:

```sh
zip -r nubia.zip nubia -x *node_modules* *bower_components* *git*
```

This will exclude *node_modules*, *bower_components*, and *git* directories from the final zip file.

---

Another option is to use the Ghost [Code Injection](https://help.ghost.org/hc/en-us/articles/223403488-Code-Injection) feature. This is great if you don’t want to touch the theme files which is recommended to receive the future theme updates without losing your customizations.

---

### Support

If you have any questions, I'd be happy to help.

* Email: [aspirethemes@gmail.com](mailto:aspirethemes@gmail.com)
* Twitter: [@aspirethemes](https://twitter.com/aspirethemes)

---