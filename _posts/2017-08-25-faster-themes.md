---
layout: post
title: How I Create Faster Themes
tags: [tips, performance]
image: '/images/posts/faster-themes/cover.jpg'
description: In this post, I will share some tips I use to achive and do high performace themes
---

Performance is one of the most important things I care about in my work creating themes. Recently, I received an inquiry email about how I achieve such a great performance record, that record could be 100% with Google Page Speed from some themes I did, for example, [Aspire](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Faspire-jekyll.aspirethemes.com%2F&tab=desktop) for Jekyll, [Aspire Themes](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Faspirethemes.com%2F) website, [Dahab](https://developers.google.com/speed/pagespeed/insights/?url=http%3A%2F%2Fdahab.aspirethemes.com%2F&tab=desktop) for Ghost.

![Create the Contact Page](/images/posts/faster-themes/email.png)

There are some things I do to help me achieve a good score which I replied to the email and I found that it would be great to share them with the community.

1. I don’t ever use CSS frameworks (Bootstrap, ...) they are very bad for performance and for coding a custom work, too much code bloat which in return make pages load slower.

2. Instead, I craft the Theme's code from scratch using Sass, ITCSS, this in return produces high quality faster and small custom code.

3. I use automation tools like Gulp to minify the final CSS and JS into only one file, and in the case of Ghost and Jekyll, the CSS is inlined in the header which would increase the performance may be 10 to 20%.

4. For the themes demos, I use the available tools everyone can use, for example, DigitalOcean for WP and Ghost and I use [Netlify](https://www.netlify.com/) for Jekyll and all with the default hosting settings. Aspire Themes is also built with Jekyll and hosted on Netlify and the score is 99 and it is open source.

5. One more important thing is that I optimize the demo images and I expect everyone should do this, but uploading big images would definitely make things worse even if the theme is 100% and Google would complain about images optimization as they play a huge role to the general score and considered outside the theme job scope. So I do my best from the theme side and then the site owner would do his best too.

So, I optimize the code very very much, optimize the images, host in a good place.

The case for WordPress, for example, is that it's loading some code that makes the score less, but if you checked the Bold for Ghost, you will get [91/97 score](https://developers.google.com/speed/pagespeed/insights/?url=http%3A%2F%2Fbold.aspirethemes.com%2F). So every time you install a new plugin to WP, performance will decrease due to the more resources loaded which are outside the theme scope.

So, with the optimized themes and the more you optimize your images, you can easily achieve the same score.