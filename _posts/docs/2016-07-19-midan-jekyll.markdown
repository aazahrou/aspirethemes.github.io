---
layout: doc
title: Midan
categories: docs
type: jekyll
---

* Name: Midan
* Description: Clean and Fast Jekyll Blog Theme
* Current Version: 1.0.0
* Released: 19 July 2016

---

## Table of Contents

* [Configurations](#configurations)
* [Deployment](#deployment)
* [Posts](#posts)
* [Pages](#pages)
* [Navigation](#navigation)
* [Disqus Comments](#disqus-comments)
* [Google Analytics](#google-analytics)
* [Social Media Links](#social-media-links)
* [Update favicon](#update-favicon)
* [Support](#support)

## Configurations

Midan theme comes with different customizations in the `_config.yml` file:

```
title: Midan
email: your-email@domain.com
description: Minimal and Clean Blog Jekyll Theme
baseurl: '' # the subpath of your site, e.g. /blog
url: 'http://aspirethemes.com' # the base hostname & protocol for your site
twitter_username: aspirethemes
github_username:  aspirethemes
instagram_username: aspirethemes

# Build settings
markdown: kramdown
gems: [jekyll-paginate]
permalink: pretty
include: [_pages]
exclude: ['Gemfile', 'Gemfile.lock']

# Pagination
paginate: 12

# Tags
tag_page_layout: tag_page
tag_page_dir: tag
tag_permalink_style: pretty

authors:
  john:
    name: John Adam
    display_name: John Adam
    bio: Adam has over 5 years of experience as a web writer, and also a photographer.
    gravatar: http://east.aspirethemes.com/content/images/2016/01/smiles-man.jpg
    email: john@aspirethemes.com
    web: http://aspirethemes.com
    twitter: aspirethemes
    github: aspirethemes
```

---

## Deployment

To run the theme locally, navigate to the theme directory and run `bundle install` to install the dependencies, then run `jekyll serve` to start the Jekyll server.

I would recommend checking the [Deployment Methods](https://jekyllrb.com/docs/deployment-methods/) page on Jekyll website.

East is [configured](https://www.aerobatic.com/docs/automated-builds#jekyll) to work with [Aerobatic](http://aerobatic.com/).

---

### Posts

To create a new post, you can create a new markdown file inside the `_posts` directory by following the [recommended file structure](https://jekyllrb.com/docs/posts/#creating-post-files).

The following is a post file with different configurations you can add as example:

```
---
layout: post
title: Welcome to Jekyll!
featured: true
author: john
tags: [python, ruby, java]
image: '/images/posts/image.jpeg'
---
```

You can set the author, featured or not, tags, and the post image.

The `featured` key is to mark the post as a featured post, this will add a simple star icon (☆) to the post card.

![featured-post](/images/docs/jekyll/east/featured-post.png)

To keep things more organized, add post images to **/images/pages** directory, and add page images to **/images/pages** directory.

To create a draft post, create the post file under the **_drafts** directory, and you can find more information at [Working with Drafts](http://jekyllrb.com/docs/drafts/).

---

### Pages

To create a new page, just create a new markdown file inside the `_pages` directory.

The following is the `about.md` file that you can find as an example included in the theme with the configurations you can set.

```
---
layout: page
title: About
permalink: /about
image: '/images/pages/about.jpeg'
---
```

Things you can change are: `title`, `permalink`, and `image` path.

---

### Navigation

The navigation on the sidebar will automatically include all the links to the pages you have created.

---

### Disqus Comments

Midan Theme comes with Disqus comments enabled.

Open `_includes/disqus.html` file, and change the `aspirethemes` value on line 15 with your [Disqus account shortname](https://help.disqus.com/customer/portal/articles/466208).

```js
s.src = '//aspirethemes.disqus.com/embed.js';
```

So, if your Disqus shortname is `exampleone`, the final code above should be

```js
s.src = '//exampleone.disqus.com/embed.js';
```

That's all you need to setup Disqus from the theme side. If you get any issue regarding that comments are unable to load. First, make sure you have [registered your website with Disqus (Step 1)](https://help.disqus.com/customer/portal/articles/466182-publisher-quick-start-guide)

And also check [Disqus troubleshooting guide](https://help.disqus.com/customer/portal/articles/472007-i-m-receiving-the-message-%22we-were-unable-to-load-disqus-%22) if you still have issues.

---

### Google Analytics

To integrate Google Analytics, open `_includes/analytics.html`, and add your Google Analytics code.

### Social Media Links

Social media links are placed in:

- `_includes/footer.html`

The theme is using [Evil Icons](http://evil-icons.io/), which contains very simple and clean icons. The following is a list of the social media icons to use:

**Twitter**

```html
<span data-icon="ei-sc-twitter" data-size="s"></span>
```

**Facebook**

```html
<span data-icon="ei-sc-facebook" data-size="s"></span>
```

**Instagram**

```html
<span data-icon="ei-sc-instagram" data-size="s"></span>
```

**Pinterest**

```html
<span data-icon="ei-sc-pinterest" data-size="s"></span>
```

**Vimeo**

```html
<span data-icon="ei-sc-vimeo" data-size="s"></span>
```

**Google-plus**

```html
<span data-icon="ei-sc-google-plus" data-size="s"></span>
```

**Soundcloud**

```html
<span data-icon="ei-sc-soundcloud" data-size="s"></span>
```

**Tumblr**

```html
<span data-icon="ei-sc-tumblr" data-size="s"></span>
```

**Youtube**

```html
<span data-icon="ei-sc-youtube" data-size="s"></span>
```

---

### Update favicon

You can find the current favicon (favicon.ico) inside the theme root directory, just replace it with your new favicon.

---

## Support

If you have any questions, I’d be happy to answer them.

* _Email:_ [aspirethemes@gmail.com](mailto:aspirethemes@gmail.com)
* _Twitter:_ [@aspirethemes](https://twitter.com/aspirethemes)