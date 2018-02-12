---
layout: doc
title: East
categories: docs
platform: WordPress
---

Current Version: 1.1.6 - 9 May 2017

---

* [Theme Activation & Installation](#theme-activation--installation)
* [Theme Customizer](#theme-customizer)
* [Widgets](#widgets)
* [Menus](#menus)
* [Translation](#translation)
* [Theme Development](#theme-development)
* [Support](#support)

---

### Theme Activation & Installation

Login to your WordPress website, go to **Appearance/Themes**, click **Add New**, then click **Upload Theme**.

![Upload Theme](/images/docs/wordpress/shared/upload-theme.png)

Upload **east.zip** file (it’s in the zip file you downloaded), then click **Install Now**

![Choose Theme](/images/docs/wordpress/shared/choose-theme-file.png)

Then click **Activate** to activate the East theme.

![Activate Theme](/images/docs/wordpress/shared/activate-theme.png)

### Installation via FTP

1. Login to the SFTP/FTP account for your site.
2. Navigate the to the WordPress directory, and follow the path **wp-content/themes.**
3. Extract **east.zip** file (it’s in the zip file you downloaded) and upload the east folder.
4. Once it’s uploaded, go to your WordPress Admin, browse to **Appearance > Themes.**
5. Click the **Activate** link.

---

## Theme Customizer

WordPress customizer is a tool which allows you to edit all the style options from a theme and visualize changes live, as you edit them. To open it go to Appearance > Customize.

![Theme Customizer](/images/docs/wordpress/east/customizer.png)

#### Logo

From the customizer window, choose **Theme Options > Header** to upload your custom logo

#### Header Search Icon

You can hide or show the header search icon as:

From the customizer window, choose **Theme Options > Header** and then **Hide Search Icon**

#### Footer Copyright

From the customizer window, choose **Theme Options > Footer** to easily update the copyright text

---

### Widgets

The East theme includes multiple widgets areas.

Widgets can be added to these areas by navigating to "Appearance > Widgets".

![Widgets](/images/docs/wordpress/east/widgets.png)

The footer section has four registered widget sections you can drag widgets in.

![footer-widgets](/images/docs/wordpress/east/footer-widgets.png)

### Menus

East theme supports two custom menus:

* Primary Menu
* Social Menu

![menus](/images/docs/wordpress/east/menus.png)

You can create and manage these menus by navigating to Appearance > Menus.

#### Primary Menu

To create the header main navigation, create a WordPress normal menu. The [WordPress Menu User Guide](https://codex.wordpress.org/WordPress_Menu_User_Guide) will describe how to create a menu, add menu items, create multi-level menu items, and more. Then you can assign the menus you just created to the Primary Menu location in the Menu Settings section

![menu-settings](/images/docs/wordpress/east/menu-settings.png)

#### Social Menu

You can create a normal menu with a custom link to the social media site. Then you can assign the menu to the Social Menu location in the Menu Settings section.

![social-media-menu](/images/docs/wordpress/east/social-media-menu.png)

The following are the social media sites and services where you can find an icon support. The theme is using [genericons](http://genericons.com/) icons.

<div class="o-grid">
  <div class="o-grid__col o-grid__col--1-3">
    <ul>
      <li>Twitter</li>
      <li>CodePen</li>
      <li>Digg</li>
      <li>Dribbble</li>
      <li>Dropbox</li>
      <li>Email</li>
      <li>Facebook</li>
      <li>Foursquare</li>
    </ul>
  </div>
  <div class="o-grid__col o-grid__col--1-3">
    <ul>
      <li>GitHub</li>
      <li>Google Plus</li>
      <li>Instagram</li>
      <li>LinkedIn</li>
      <li>Path</li>
      <li>Pinterest</li>
      <li>Polldaddy</li>
      <li>Reddit</li>
    </ul>
  </div>
  <div class="o-grid__col o-grid__col--1-3">
    <ul>
      <li>RSS</li>
      <li>StumbleUpon</li>
      <li>Tumblr</li>
      <li>Twitch</li>
      <li>Twitter</li>
      <li>Vimeo</li>
      <li>Vine</li>
      <li>WordPress</li>
    </ul>
  </div>
</div>

---

### Translation

The East theme is fully ready to be translated into other languages and could be easily translated with [poedit.net](https://poedit.net/) application.

The theme contains the main translation file `east.pot` inside the languages directory which will be used by the poedit application.

**Here are simple steps:**

1. Install poedit and open it.
2. Once the app is opened click Create new translation.
3. Choose the **east.pot** file inside the theme **east/language** directory.
4. Once the translation is done, save the file according to your language code. Find a list of language codes at [WordPress in your Language](https://make.wordpress.org/polyglots/teams/). As an example, the language code for English (UK) is `en_GB`, so you will end up with two new files: `en_GB.po` and then `en_GB.mo`.
5. When that’s done, simply upload the files to **east/language** folder using FTP.
6. Change the site language by going to `WordPress > General > Settings` and choose the target language from `Site Language` drop-down menu.

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