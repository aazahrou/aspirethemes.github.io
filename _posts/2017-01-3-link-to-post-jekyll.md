---
layout: post
title: Create a link to a post in Markdown in Jekyll
tags: [jekyll, markdown]
image: '/images/posts/jekyll-links/jekyll.png'
---

Recently I got a support request from a client about how to link to an internal post with Jekyll. The use case for this when you are writing a post and you want to link to another post the Jekyll way without hard coding the full URL. I did some research and I found that Jekyll has a very elegant way to do that, and I would like to share this good tip with you.

Linking to an internal post is as simple as the following snippet:

{% highlight html %}
{% raw %}
[Name of Link]({{ site.baseurl }}{% post_url 2010-07-21-name-of-post %})
{% endraw %}
{% endhighlight %}

The snipet is a markdown syntax just as normal URL `post_url` tag which will automatically generate the post URL for you.

Hope this tip is useful and you can read more about this and more options on the [Jekyll documentation](http://jekyllrb.com/docs/templates/#post-url).