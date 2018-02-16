---
layout: post
title: Create Your Own Public Slack Chat Community With Slackin
tags: [community, tips, slack]
image: '/images/posts/slack/slakin-banner.png'
---

I was looking to create a Slack channel for [Aspire Themes](https://aspirethemes.com/?utm_source=medium&utm_medium=articles) where I and my customers can discuss, share, and get fast support with Slack. The one thing I worried about is how anyone can get an invitation and join the channel easily.

I found [Slackin](https://github.com/rauchg/slackin) to be a great solution, it creates a public landing page for users to fill their email to receive a Slack invitation.

![Slakin](/images/posts/slack/slakin-banner.png)

#### Prepare Slack

* Create a new team on [Slack](https://slack.com/).
* Create a new [API token](https://get.slack.help/hc/en-us/articles/215770388-Create-and-regenerate-API-tokens) to the team.

#### Deployment

* Install the [Now](https://zeit.co/download#command-line) command line interface for with NPM.

{% highlight shell %}
npm install -g now
{% endhighlight %}

Next, from the command line, use the following [command](https://github.com/rauchg/slackin#usage) to deploy [Slackin](https://github.com/rauchg/slackin) to [ZEIT](https://zeit.co/), using the API token and the team name you early created.

{% highlight shell %}
now -e SLACK_API_TOKEN="<token>" -e SLACK_SUBDOMAIN="<team-name>" now-examples/slackin
{% endhighlight %}

<figure markdown='1'>
![Deploy to ZEIT](https://cdn-images-1.medium.com/max/1000/1*Jdu14gnFx5vvGGOO6FrTyQ.png)
</figure>

That’s all you need to do, and once the app is deployed, a new URL ([example](https://now-examples-slackin-hzqfnemqkc.now.sh/)) for the landing page will be created and ready to share.

1. **Landing Page** (***[Demo](http://now-examples-slackin-hzqfnemqkc.now.sh/)***)

<figure markdown='1'>
![Slakin Landing Page](/images/posts/slack/slakin-landing-page.png)
<figcaption markdown='1'>
Image [Credit](https://www.producthunt.com/posts/slackin-2#comment-87632)
</figcaption>
</figure>

2. **Badge** (***[Demo](http://now-examples-slackin-hzqfnemqkc.now.sh/badge.svg)***)

![Slakin Badge](/images/posts/slack/slakin-badge.jpg)

3. **[Realtime Subscription](https://github.com/rauchg/slackin#realtime-demo)** ***([Demo](https://jsbin.com/xoqoxaleke/edit?output)***)

<figure markdown='1'>
![Slakin Badge](/images/posts/slack/slakin-realtime.gif)
<figcaption markdown='1'>
Image [Credit](https://www.producthunt.com/posts/slackin-2#comment-87632)
</figcaption>
</figure>

The landing page URL will be similar to [now-examples-slackin-hzqfnemqkc.now.sh](https://now-examples-slackin-hzqfnemqkc.now.sh/), and of course, customizing this URL to a subdomain would be another great step. I think [ZITE Premium](https://zeit.co/now#pricing) enables custom domain support, for now, I created a Masked URL Redirect Record with [NameCheap](http://bit.ly/aspire-namecheap) and by doing this I can access the landing page from [slack.aspirethemes.com](http://slack.aspirethemes.com/)

<figure markdown='1'>
![Masked URL Redirect Record](/images/posts/slack/domain-redirect.png)
<figcaption>Masked URL Redirect Record</figcaption>
</figure>

I hope this will help you create your next Slack Channel, and if there any tips or recommendations you like to share, I would be happy to hear and learn from you.

***Also published on [Medium](https://medium.com/aspirethemes/create-your-own-public-slack-chat-community-with-slackin-1825c1d3efb2#.98jzi2xiz).***