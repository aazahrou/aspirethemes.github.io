---
layout: doc
title: Maxima
categories: docs
platform: Jekyll
---

Current Version: 1.0.7 - 18 May 2017

---

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

---

### Configurations

Maxima theme comes with different customizations in the `_config.yml` file:

```sh
# Site settings
title:              Maxima
logo:               # Logo image URL
email:              your-email@domain.com
description:        Minimal Blog & Magazine Jekyll Theme
baseurl:            '' # The subpath of your site, e.g. /blog
url:                'http://maxima-jekyll.aspirethemes.com' # The base hostname & protocol for your site
github_username:    aspirethemes
twitter_username:   aspirethemes
instagram_username: aspirethemes

markdown:  kramdown
permalink: pretty
paginate:  13
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
    bio:              Author & developer of Aspire Themes
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

The following is a post file with different configurations you can add as an example:

```sh
---
layout: post
title: Welcome to Jekyll!
featured: true
author: ahmad
tags: [frontpage, jekyll, blog]
image: '/images/welcome.jpg'
---
```

You can set the author, featured or not, tags, and the post image.

The `featured` key is to mark the post as a featured post, this will add a simple star icon (☆) to the post card.

<figure markdown='1'>
![featured-post](/images/docs/jekyll/maxima/featured-post.png)
</figure>

To keep things more organized, add post images to **/images/pages** directory, and add page images to **/images/pages** directory.

To create a draft post, create the post file under the **_drafts** directory, and you can find more information at [Working with Drafts](http://jekyllrb.com/docs/drafts/).

For tags, try to not add space between two words, for example, `Ruby on Rails`, could be something like (`ruby-on-rails`, `Ruby_on_Rails`, or `Ruby-on-Rails`).

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

Maxima Theme comes with Disqus comments enabled.

Open `_includes/disqus.html` file, and change the `aspirethemes` value on line 15 with your [Disqus account shortname](https://help.disqus.com/customer/portal/articles/466208).

```js
s.src = '//aspirethemes-demo.disqus.com/embed.js';
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

* `_includes/footer.html`

The theme is using [Evil Icons](http://evil-icons.io/), which contains very simple and clean icons. The following is a list of the social media icons to use:

{% include evil-icons.liquid %}

---

### Update favicon

You can find the current favicon (favicon.ico) inside the theme root directory, just replace it with your new favicon.

---

### Support

If you have any questions, I'd be happy to help.

* Email: [aspirethemes@gmail.com](mailto:aspirethemes@gmail.com)
* Twitter: [@aspirethemes](https://twitter.com/aspirethemes)

---