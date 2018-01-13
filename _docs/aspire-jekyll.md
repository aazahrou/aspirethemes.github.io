---
layout: doc
title: Aspire
categories: docs
platform: Jekyll
---

Current Version: 1.0.1 - 28 Sept 2017

---

* [Configurations](#configurations)
* [Deployment](#deployment)
* [Posts](#posts)
* [Pages](#pages)
* [Navigation](#navigation)
* [Disqus Comments](#disqus-comments)
* [Twitter](#twitter)
* [Instagram](#instagram)
* [MailChimp](#mailchimp)
* [Google Analytics](#google-analytics)
* [Social Media Links](#social-media-links)
* [Update favicon](#update-favicon)
* [Support](#support)

---

### Configurations

Aspire theme comes with different customizations in the `_config.yml` file:

```sh
# Site settings
title:              Aspire
logo:               # Logo image URL
description:        Clean News & Magazine Jekyll Theme
baseurl:            '' # The subpath of your site, e.g. /blog
url:                'http://aspire-jekyll.aspirethemes.com' # The base hostname & protocol for your site
twitter:            https://twitter.com/aspirethemes
facebook:           https://www.facebook.com/aspirethemes/
instagram:          https://www.instagram.com/aspirethemes

markdown:  kramdown
permalink: pretty
paginate:  9
sass:
  style: compressed

gems:
  - jekyll-paginate
  - jekyll/tagging

include:
  - _pages

exclude:
  - vendor
  - Gemfile
  - Gemfile.lock

# Tags
tag_page_dir:         tag
tag_page_layout:      tag_page
tag_permalink_style:  pretty

# Pages path
defaults:
  - scope:
      path: '_pages'
    values:
      permalink: /:basename:output_ext

# Authors
authors:
  ahmad:
    name:             Ahmad Ajmi
    bio:              Author & developer of Aspire Themes. Minimalist. I love creating clean and minimal websites.Technical writer at SitePoint.
    gravatar:         https://s.gravatar.com/avatar/f83141edd9e6339e678648596a403fd5?s=150
    email:            info@aspirethemes.com
    website:          http://aspirethemes.com
    github_username:  ahmadajmi
    twitter_username: ahmadajmi
```

---

### Deployment

To run the theme locally, navigate to the theme directory and run `bundle install` to install the dependencies, then run `jekyll serve` to start the Jekyll server.

I would recommend checking the [Deployment Methods](https://jekyllrb.com/docs/deployment-methods/) page on Jekyll website.

---

### Posts

To create a new post, you can create a new markdown file inside the `_posts` directory by following the [recommended file structure](https://jekyllrb.com/docs/posts/#creating-post-files).

The following is a post file with different configurations you can add as example:

```sh
---
layout: post
title: Welcome to Jekyll!
featured: true
author: ahmad
tags: [frontpage, jekyll, blog]
image: '/images/posts/welcome.jpg'
---
```

You can set the author, featured or not, tags, and the post image.

The `featured` key is to mark the post as a featured post, this will add a simple star icon (☆) to the post card.

<figure markdown='1'>
![featured-post](/images/docs/jekyll/aspire/featured-post.png)
</figure>

To keep things more organized, add post images to **/images/pages** directory, and add page images to **/images/pages** directory.

To create a draft post, create the post file under the **_drafts** directory, and you can find more information at [Working with Drafts](http://jekyllrb.com/docs/drafts/).

For tags, try to not add space between two words, for example, `Ruby on Rails`, could be something like (`ruby-on-rails`, `Ruby_on_Rails`, or `Ruby-on-Rails`).

As mentioned in the [item page](https://themeforest.net/item/aspire-clean-news-magazine-jekyll-theme/19847658), there is a problem with tags when the site is deployed using GitHub Pages, as the tagging gem is not supported, but I managed to fix this by using [Netlify](https://www.netlify.com/) for deployment, the code will be on GitHub or BitBucket as usual, it's only one step to connect the repo and do the deployment, just a fantastic service I use for all of my Jekyll work. This [post](https://www.netlify.com/blog/2017/05/11/migrating-your-jekyll-site-to-netlify/) is a good start.

---

### Pages

To create a new page, just create a new markdown file inside the `_pages` directory.

The following is the `about.md` file that you can find as an example included in the theme with the configurations you can set.

```sh
---
layout: page
title: About
image: '/images/pages/about.jpeg'
---
```

Things you can change are: `title` and `image` path.

---

### Navigation

The navigation on the sidebar will automatically include all the links to the pages you have created.

---

### Disqus Comments

Aspire Theme comes with Disqus comments enabled.

Open `_includes/disqus.html` file, and change the `aspirethemes` value on line 15 with your [Disqus account shortname](https://help.disqus.com/customer/portal/articles/466208).

```js
s.src = '//aspirethemes-demos.disqus.com/embed.js';
```

So, if your Disqus shortname is `exampleone`, the final code above should be

```js
s.src = '//exampleone.disqus.com/embed.js';
```

That's all you need to setup Disqus from the theme side. If you get any issue regarding that comments are unable to load. First, make sure you have [registered your website with Disqus (Step 1)](https://help.disqus.com/customer/portal/articles/466182-publisher-quick-start-guide)

And also check [Disqus troubleshooting guide](https://help.disqus.com/customer/portal/articles/472007-i-m-receiving-the-message-%22we-were-unable-to-load-disqus-%22) if you still have issues.

---

### Twitter

To set up the Twitter feed:

* Go to [publish.twitter.com](https://publish.twitter.com/).
* Enter a Twitter URl into the input box and press *Enter*.
* Select *Embedded Timeline*.
* You will see a Timeline preview and you can customize it as required.
* Copy the code by clicking the *Copy Code* button.
* Open `_includes/sidebar/widget-twitter.html` file and replace line **4** with the copied code.
* Save and you are done.

<script src="//fast.wistia.com/embed/medias/yny59lxsto.jsonp" async></script><script src="//fast.wistia.com/assets/external/E-v1.js" async></script><div class="wistia_responsive_padding" style="padding:55.31% 0 0 0;position:relative;"><div class="wistia_responsive_wrapper" style="height:100%;left:0;position:absolute;top:0;width:100%;"><div class="wistia_embed wistia_async_yny59lxsto videoFoam=true" style="height:100%;width:100%">&nbsp;</div></div></div>

---

### Instagram

The Instagram feed is working using [Instafeed.js](http://instafeedjs.com/) to show the photos.

First, you will need to get your account `userId` and `accessToken` from the following URLs:

- userId: [smashballoon.com/instagram-feed/find-instagram-user-id](https://smashballoon.com/instagram-feed/find-instagram-user-id/)
- accessToken: [instagram.pixelunion.net](http://instagram.pixelunion.net/)

Second, open the `js/app.js` file and replace the `userId` and `accessToken` values.

```js
var instagramFeed = new Instafeed({
  get: 'user',
  limit: 9,
  resolution: 'thumbnail',
  userId: '',
  accessToken: ''
});
```

You can control how much images to show by changing the `limit` number. Theme default is set to `9` images.

---

### MailChimp

Steps to integrate [MailChimp](http://mailchimp.com/) newsletter subscription form:

* Create a mailing list from your MailChimp account, fill all the fields required and save it.
* From the mailing list page, select **Signup forms**, then select **Embedded forms**.
* Under the preview section, you will find the mailing form code. You will only need the form action value, like the highlighted code in the image blow.

![mailchimp-code](/images/docs/jekyll/shared/mailchimp-code.png)

* Copy that code and replace it with the current form action value located in `_includes/subscribe-form.html` file.

![mailchimp-code](/images/docs/jekyll/aspire/subscribe-form.png)

You are done.

---

### Google Analytics

To integrate Google Analytics, open `_includes/analytics.html`, and add your Google Analytics code.

### Social Media Links

Social media links are placed in:

* `_includes/social-nav.html`
* `_includes/sidebar/widget-social.html`
* `_includes/footer.html`

The theme is using [Evil Icons](http://evil-icons.io/), which contains very simple and clean icons. The following is a list of the social media icons to use:

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

---

### Update favicon

You can find the current favicon (favicon.ico) inside the theme root directory, just replace it with your new favicon.

---

### Support

If you have any questions, I'd be happy to help.

* Email: [aspirethemes@gmail.com](mailto:aspirethemes@gmail.com)
* Twitter: [@aspirethemes](https://twitter.com/aspirethemes)

---