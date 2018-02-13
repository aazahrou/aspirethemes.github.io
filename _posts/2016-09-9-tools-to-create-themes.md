---
layout: post
title: Tools I Use to Create Premium WordPress and Ghost Themes
tags: [Tools, WordPress, Ghost]
image: '/images/posts/tools/tools.png'
---

At [Aspire Themes](http://aspirethemes.com/) I use a lot of tools to help me create WordPress, Ghost and Jekyll themes. Tools will range from development, design, services, hosting and automation tools for making my life easier as a one man shop, and It might be helpful for someone else in a way or another starting their journey as a theme creator or a developer; so I’m so happy to share them with you.

### Mamp

I use [Mamp](https://www.mamp.info/) to run my development WordPress installation on Mac, it’s very easy to use and I use the free version and it did what I need.

### Bitnami

This service is just awesome, I use the [Ghost Stack](https://bitnami.com/stack/ghost) to install Ghost locally. This saves a lot of time and headache installing Ghost, and by using it , we I avoid issues like *Node.js* versions conflicts and issues regarding *npm* installation and other infinite numbers of issues. The Bitnami stack provides a one-click install solution for Ghost, and with a few minutes you will have Ghost installed and ready for working.

### Visual Studio Code

I used to use Sublime before, but after I discovered [Visual Studio Code](https://code.visualstudio.com/), I switched to it from the first usage, it’s very fast, smooth, huge community with lots of [extensions](https://marketplace.visualstudio.com/VSCode) and gets updates regularly, and I totally recommend checking it out.

### iTerm + tmux

[iTerm](https://www.iterm2.com/) is a replacement to Mac terminal, and I think most of you are using it for Mac.

[tmux](https://tmux.github.io/) is a terminal multilpexer and a pretty great tool.

**What is a terminal multiplexer?**

> It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. And do a lot more.

It saves a lot of time by letting you focus on one terminal, create more sessions and more windows as you need on that session, very flexible and will change the way you work with the terminal.

### BashScript

I wrote a post explaining how I use BashScript to automate theme deployment to remote servers, which is a time saver for me, especially on testing themes while doing development.

### Git

[Git](https://git-scm.com/) should be one of the first things to learn as a developer. Currently, I use the [git-flow workflow](http://nvie.com/posts/a-successful-git-branching-model/) which is a great way to organize and manage the way I work with branches, adding new features, fixing bugs, .. etc

### BitBucket

By using Git it’s very important to host all the themes and work on a remote server like [GitHub](https://github.com/) or [BitBucket](http://bitbucket.org/).

I use BitBucket to host my work as it’s a free option with unlimited private repos.

### Pixelmator

[Pixelmator](http://www.pixelmator.com/mac/) is a great image editor for Mac, I use it all the time to create themes preview images, and any image customization I need. Pixelmator costs about $30.

### iOS Simulator

A few weeks ago I received an email from a client who purchased the [Magaz](https://aspirethemes.com/themes/magaz-ghost.html) Ghost theme and found an issue on iPad regarding the posts grid on the home page. I tried to debug the issue on the Chrome dev tools as I don’t have an iPad, but I wasn’t able to reproduce the issue. I remembered that I have tried the iOS Simulator that comes with xCode; so I opened the simulator and picked iPad Device from the Hardware menu, and now I can see the issue.

The great thing about the Simulator is that I can test the web page natively on different devices and also debug with Safari dev tools and this is a big win for using the iOS Simulator.

![Testing on iPhone 6 Plus/iOS 8.3 & Debugging with Safari Dev Tools](/images/posts/tools/tools.png)

### Gulp

[Gulp](http://gulpjs.com/) is a JavaScript task runner that could save a lot of time while developing themes, and it’s one of the most important tools I use, for assets automation, I use it with Sass, JavaScipt, and everything that I think I do repeat a lot and I should automate it instead.

I also use it to generate the *rtl.css* file that is used for WordPress RTL sites, you can read more about this in a post I wrote before.

You can check a real example of a *gulpfile.js* I use at [GitHub](https://gist.github.com/ahmadajmi/c8540178238a6e36601f690e818e7448).

### Sass

[Sass](http://sass-lang.com/) is a powerful tool for writing modular and organized CSS, organizing the source code into components, sections, and variables makes life easier for developers instead of one big file of CSS, using variables, mxins and other features will change the way you write raw CSS.

I have shared the Sass code example for the recent [Real Ghost theme](https://aspirethemes.com/themes/real-ghost.html), you can check it out at [GitHub](https://github.com/ahmadajmi/sass-example).

### WordPress Tools

For better WordPress development and for getting great results and to make sure themes are coded with best practices and validated, there are some plugins and tools that are essentials in my workflow.

[Developer Plugin](http://wordpress.org/extend/plugins/developer/): This is the first plugin to install to check and optimize the development environment for tools and plugins that will help you develop better themes with a better quality.

[RTL Tester](https://wordpress.org/plugins/rtl-tester/): If you support RTL I’m doing, then this plugin is a must as it tests themes in RTL mode.

[Theme Check](https://wordpress.org/plugins/theme-check/): To make sure that the theme is compatible with WordPress standards, this is an amazing plugin to be in your arsenal.

[Theme Unit Test](https://codex.wordpress.org/Theme_Unit_Test): Which generates some dummy content data for testing all kinds of content. I also recommend you to add some real content with good looking images that feels like a content other than unreadable text like Lorem Ipsum.

[The Monster Widget](http://wordpress.org/extend/plugins/monster-widget/): This plugin will add all core widgets to the sidebar for testing, which is perfect for optimizing widget styles in different places, so if you support widgets in the footer make sure to activate this widget there to make sure that all widgets styles are looking as you want in different places.

[ManageWP](https://managewp.com/): A great online tool to manage WordPress websites from one dashboard, I use it mainly to update plugins for themes demos, which saves me lots of time opening every site to do the updates.

## Hosting

An important thing about creating premium themes is to create a complete demo site for the theme, and of course, you need a hosting service for creating a demo for every single theme, I have tried several options and here are the ones I currently use.

### DigitalOcean

I use [DigitalOcean](https://www.digitalocean.com/) to host WordPress and Ghost themes. For WordPress, I created a Droplet and connected it with the awesome [ServerPilot](https://serverpilot.io/) service, which makes creating WordPress sites as speed as a rocket. Currently, I host all WordPress demos (5 demos) on one $5 Droplet.

I also host 5 Ghost demos on one 5$ Droplet, this absolutely saves a lot of time and energy managing all the instances if they are in separate droplets, plus it is a very cost effective.

You can read about how to host multiple instances in the following article.

### Aerobatic

[Aerobatic](https://www.aerobatic.com/) used to host Jekyll themes and a great thing about it is the integration with [BitBucket](http://bitbucket.org/). [Aerobatic](https://www.aerobatic.com/) is very easy to setup with Jekyll. The free plan is limited to 5 deployments in a 24 hour period, but this is working fine for me with no issue.

### Jekyll

I use Jekyll for [Aspire Themes](http://aspirethemes.com/) website which includes several sections like the [blog](http://aspirethemes.com/blog/), [documentations](http://aspirethemes.com/docs/), [about](http://aspirethemes.com/about/), and the [themes](http://aspirethemes.com/themes/) page with a separate page for every theme. The source code is available on [GitHub](https://github.com/aspirethemes/aspirethemes.github.io).

Jekyll is very flexible in the way you can structure your site as needed and all is done in text, no databases, no queries, just a simple markup language and markdown files — which we love as developers — and then you can host the site for free on [GitHub Pages](https://pages.github.com/).

I also started to use [Netlify](https://www.netlify.com/) service for deployment, and with a few minutes, you can add a free SSL certificate to the website.

![HTTPS enabled by Netlify for aspirethemes.com](/images/posts/tools/aspirethemes.png)

I will write a post about how I built the website and how the structure is going.

### Namecheap

I started to use [Namecheap](https://www.namecheap.com/) recently and I like their services and the web dashboard interface is very understandable and easy to use. They also provides a great online customer support, and I recommend them if you are looking to buy a new domain.

I hope you find the post useful exploring a new tools and tips that I use on day to day work, that will help you start your next theme shop or even use them in your daily development workflow. Let me know if there any tools you can recommend if you are a theme author or a developer, also if you have any questions, I would be happy to discuss them with you.