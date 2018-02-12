---
layout: doc
title: Bold
categories: docs
platform: Ghost
---

Current Version: 1.1.4 - 07 December 2017

---

* [Theme Installation](#theme-installation)
* [Enable the Public API](#enable-the-public-api)
* [Static Pages](#static-pages)
* [Header](#header)
* [Navigation](#navigation)
* [Home Hero](#home-hero)
* [Search](#search)
* [Tags Page](#tags-page)
* [Disqus Comments](#disqus-comments)
* [Instagram](#instagram)
* [Subscribe Form](#subscribe-form)
* [Posts Per Page](#posts-per-page)
* [Related Posts](#related-posts)
* [Google Analytics](#google-analytics)
* [Social Media Links](#social-media-links)
* [Update Favicon](#update-favicon)
* [Theme Development](#theme-development)
* [Support](#support)

---

### Theme Installation

This is a quick video showing how to install the theme, upload blog cover image, favicon, create the tags page, and update the profile information for the editor.

<iframe src='https://www.youtube.com/embed/vCmuGncWubQ' frameborder='0' allowfullscreen></iframe>

---

Also, you can follow the following steps to install the theme:

* Log into the admin section of your Ghost blog `yourblog.com/ghost`.
* Select `Design` from the left-hand side of your admin area and scroll to the bottom **Themes** section.
* Click on the `Upload a Theme` green button.
* An upload box will open, then choose the theme (*bold.zip*) within the downloaded package.
* Once uploaded, click on `Activate now` button to activate the theme immediately or `Close` if you want to activate it later.

---

### Enable the Public API

Public API is important for some functionality like search, tags page, and subscribe form to work properly. You can enable the Public API from Ghost admin. Go to `Labs > Beta features` section and check the *Public API* mark to enable it.

![enable-public-api](/images/docs/ghost/shared/beta-features.png)

---

### Static Pages

In order to create a static page, you create a new post, just like you would any other post. Once you have opened up the new post, there is a cog wheel icon next to where it says "Save Draft" or "Update Post" depending on if you have published the post or not. Click on that cog, and check the "Turn this post into a static page" box. This will convert your post to a static page.

![static page](/images/docs/ghost/bold/static-page.png)

---

### Header

![header left logo code](/images/docs/ghost/bold/header-left-logo.png)

If you want to enable the left logo alternative header layout, open the `partials/header.hbs` file and add the `c-header--left-logo` to the header class and that's all that you need to do.

![header left logo](/images/docs/ghost/bold/header-left-logo-code.png)

---

### Navigation

You can add, edit, delete and reorder menu links on your Ghost blog, directly from the navigation tool within the blog admin area, located at **/ghost/settings/navigation/**.

![navigation menu](/images/docs/ghost/bold/navigation-edit.png)

To include a static page on your navigation menu, first, type the name of the page as you'd like it to appear on your menu in the label field.

![label field](/images/docs/ghost/bold/label-field.png)

Next, click inside the **URL field** of the menu item. The blog URL will auto-populate with http://yourdomain.com/. You will need to add in the page slug after the final **/**. Once satisfied with your page link, click the blue **Save button** to add the page to the navigation menu.

---

### Home Hero

![home hero](/images/docs/ghost/bold/home-hero.png)

The hero section shows the cover image and the blog description, which you can edit from the [Blog Settings](https://help.ghost.org/hc/en-us/articles/223207167-Blog-Settings-Overview) admin page.

The theme comes with description support for HTML tags, so you can add normal tags like custom links or headings and the theme will automatically render them on the browser. For example, the demo description is the following:

```html
<h2>Thoughts, Stories and Ideas.</h2>
<p>Don't cry because it's over, smile because it happened.
  <br>
  - <a href='https://en.wikipedia.org/wiki/Dr._Seuss'>Dr. Seuss</a>
</p>
```

---

### Search

For the search to work properly, please make sure that the [Public API](#enable-the-public-api) is enabled.

---

### Tags Page

To create the tags page:

- Enable the [Public API](#enable-the-public-api).
- Create a new post and call it `Tags` for example, and make sure that the POST URL is `tags`.
- Click the `Turn this post into a static page` checkbox.
- Publish the page.
- To add the page to the navigation, please check the [Navigation](#navigation) section above.

![static page](/images/docs/ghost/bold/tags-page.png)

---

### Disqus Comments

The Theme comes with Disqus comments enabled.

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

#### Disable Disqus

If you want to disable Disqus comments, open the `post.hbs` file and comment or delete the line contains the `{% raw %}{{> disqus}}{% endraw %}` text (line 31).

![enable subscribers](/images/docs/ghost/bold/disable-disqus.png)

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
  limit: 98,
  resolution: 'thumbnail',
  userId: '',
  accessToken: ''
});
```

You can control how much images to show by changing the `limit` number. Theme default is set to `8` images.

---

### Subscribe Form

Subscribers can be enabled via a checkbox on the Labs page (`Labs > Beta features`), in your Ghost admin panel:

![enable subscribers](/images/docs/ghost/shared/beta-features.png)

Once you enabled this feature, the form will appear in the single post page and the footer.

You can read more about [Subscribers Beta](https://help.ghost.org/hc/en-us/articles/224089787-Subscribers-Beta).

---

### Posts Per Page

With Ghost 1.0, the ["Posts per page"](https://themes.ghost.org/docs/packagejson#section--config-posts_per_page-) setting is now part of the theme. The config purpose is to control how many posts to show per page from the `package.json` file like this:

```json
"config": {
  "posts_per_page": 6
}
```

Bold theme default value is set to `6` posts per page.

---

### Related Posts

Related posts will be visible on the single post page when there are similar posts with similar tags, and will be hidden otherwise.

Enabling the [Public API](#enable-the-public-api) is required.

---

### Google Analytics

To integrate Google Analytics, I would recommend reading [Google Analytics](https://help.ghost.org/hc/en-us/articles/115000450512-Google-Analytics) integration steps by Ghost.

---

### Social Media Links

Social media links are placed in:

* `partials/social-nav.hbs`

Ghost supports adding Facebook and Twitter profile URLs from the admin panel, go to **General > Social accounts** and add your URLs, this will update the Facebook and Twitter URLs within the location mentioned above.

![social-accounts](/images/docs/ghost/shared/social-accounts.png)

For using other social accounts, the theme is using [Evil Icons](http://evil-icons.io/), which contains very simple and clean icons. Here you can find a list of the social media icons to use:

Facebook

```html
<span class='c-social-nav__icon' data-icon='ei-sc-facebook' data-size='s'></span>
```

GitHub

```html
<span class='c-social-nav__icon' data-icon='ei-sc-github' data-size='s'></span>
```

Google Plus

```html
<span class='c-social-nav__icon' data-icon='ei-sc-google-plus' data-size='s'></span>
```

Instagram

```html
<span class='c-social-nav__icon' data-icon='ei-sc-instagram' data-size='s'></span>
```

LinkedIn

```html
<span class='c-social-nav__icon' data-icon='ei-sc-linkedin' data-size='s'></span>
```

Odnoklassniki

```html
<span class='c-social-nav__icon' data-icon='ei-sc-odnoklassniki' data-size='s'></span>
```

Pinterest

```html
<span class='c-social-nav__icon' data-icon='ei-sc-pinterest' data-size='s'></span>
```

Skype

```html
<span class='c-social-nav__icon' data-icon='ei-sc-skype' data-size='s'></span>
```

SoundCloud

```html
<span class='c-social-nav__icon' data-icon='ei-sc-soundcloud' data-size='s'></span>
```

Telegram

```html
<span class='c-social-nav__icon' data-icon='ei-sc-telegram' data-size='s'></span>
```

Tumblr

```html
<span class='c-social-nav__icon' data-icon='ei-sc-tumblr' data-size='s'></span>
```

Twitter

```html
<span class='c-social-nav__icon' data-icon='ei-sc-twitter' data-size='s'></span>
```

Vimeo

```html
<span class='c-social-nav__icon' data-icon='ei-sc-vimeo' data-size='s'></span>
```

VK

```html
<span class='c-social-nav__icon' data-icon='ei-sc-vk' data-size='s'></span>
```

Youtube

```html
<span class='c-social-nav__icon' data-icon='ei-sc-youtube' data-size='s'></span>
```

To edit or update other excisted and static social links, let's take an example from `partials/social-nav.hbs` file, for exmaple, the Instagram code block:

```html
<li class='c-social-nav__item'>
  <a href='#' aria-label='Instagram' target='_blank' rel='noopener'>
    <span class='c-social-nav__icon' data-icon='ei-sc-instagram' data-size='s'></span>
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
<li class='c-social-nav__item'>
  <a href='https://www.instagram.com/ghost/' aria-label='Instagram' target='_blank' rel='noopener'>
    <span class='c-social-nav__icon' data-icon='ei-sc-instagram' data-size='s'></span>
  </a>
</li>
```

If you want to completely remove Instagram, you can delete all the code block, the `li`, `a`, and the icon.

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
zip -r bold.zip bold -x *node_modules* *bower_components* *git*
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