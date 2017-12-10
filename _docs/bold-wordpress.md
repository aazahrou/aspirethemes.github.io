---
layout: doc
title: Bold
status: review
categories: docs
platform: WordPress
---

Current Version: 1.0.3 - 10 Dec 2017

---

* [Theme Activation & Import Demo Data (Video)](#theme-activation--import-demo-data-video)
  * [Installation via WordPress Theme Installer](#installation-via-wordpress-theme-installer)
  * [Installation via FTP](#installation-via-ftp)
  * [Import Demo Data](#import-demo-data)
* [Theme Customizer](#theme-customizer)
* [Adding Posts](#adding-posts)
* [Adding Pages](#adding-pages)
* [Widgets](#widgets-1)
* [Menus](#menus-1)
* [Home Hero](#home-hero)
* [Contact Page](#contact-page)
* [Galleries](#galleries)
* [Translation](#translation)
* [Theme Development](#theme-development)
* [Support](#Support)

---

### Theme Activation & Import Demo Data (Video)

This is a quick video showing how to install the theme and import the demo content. For installation steps, you can check the process below.

<iframe src='https://www.youtube.com/embed/TZED01pBVTY' frameborder='0' allowfullscreen></iframe>

---

### Installation via WordPress Theme Installer

1. Login to your WordPress Dashboard, go to **Appearance → Themes**.
2. At the top, click **Add New**, then click **Upload Theme**.
3. Choose the **bold.zip** zip file you will find within the whole package that you downloaded from Themforest.
4. Click **Install Now**.
5. The last step is to click **Activate** once all the files are correctly uploaded.

![Upload Theme](/images/docs/wordpress/shared/upload-theme.png)

![Choose Theme](/images/docs/wordpress/shared/choose-theme-file.png)

![Activate Theme](/images/docs/wordpress/shared/activate-theme.png)

---

### Installation via FTP

1. Login to the SFTP/FTP account for your site.
2. Navigate the to the WordPress directory, and follow the path **wp-content/themes**.
3. Extract **bold.zip** file (it’s in the zip file you downloaded) and upload the bold folder.
4. Once it’s uploaded, go to your WordPress Dashboard, browse to **Appearance > Themes**.
5. You will see the screenshot for Bold theme, just click the **Activate** link and you are ready to go.

---

### Import Demo Data

The theme comes with the demo content that you can import with one click button.

First, you will need to install the [One Click Demo Import](https://wordpress.org/plugins/one-click-demo-import/) plugin then activate it.

Second, go to **Appearance > Import Demo Data** and click the **Import Demo Data** button. It will take a few seconds, then you are done and have the demo content installed.

![Import Demo Data](/images/docs/wordpress/shared/demo-import.png)

---

### Theme Customizer

WordPress customizer is a tool which allows you to modify the look and feel of your website, you can see the changes live as you edit the options. To open it, go to **Appearance > Customize**.

![Theme Customizer](/images/docs/wordpress/bold/customizer.png)

##### Site Identity

This is where you can set different things:

1. Upload a site logo.
2. Set the Site Title and Tagline.
3. Set the footer copy right content, this support HTML coding, if this is not set, the copyright will be as like `© 2017 Bold`.
4. You can also hide or show the header search icon.
5. Display or hide Site Title and Tagline on the [Home Hero](#home-hero) section.
6. Upload the site icon (favicon) which is used as a browser and app icon for your site.

##### Header Image

In this section, you can set the Header Image which will then bu used in the [Home Hero](#home-hero) section.

##### Menus

Here you can create a new menu, add links to it set the menu location.

##### Widgets

This will help you control the widgets which are supported in the site footer, you can add new widget or remove one.

##### Static Front Page

Here you can set the homepage for your website. It could be the blog page with a list of posts, ot it could be a page like the about page for example.

##### Additional CSS

This is a great place if you want to add more CSS stylying to your website.

---

### Adding Posts

- Go to **Posts → Add New**.
- Add a title.
- Select a post Category.
- Add some relevant Tags.
- Choose a Featured Image.
- Write your post content in the content area.
- Click **Publish** and you're all done.

![Adding New Post](/images/docs/wordpress/bold/adding-new-post.png)

![Create New Post](/images/docs/wordpress/bold/create-new-post.png)

---

To create the excerpt content on the post card, put your cursor where you want to end the excerpted content of your post and click the **more** quicktag button.

![Excerpet Button](/images/docs/wordpress/bold/excerpet-button.png)

![Excerpet Button Action](/images/docs/wordpress/bold/excerpet-button-action.png)

![Excerpet Content Card](/images/docs/wordpress/bold/excerpet-content-card.png)

---

### Adding Pages

- Go to **Pages → Add New**.
- Add a title.
- Set the **Page Attributes** like the *Parent* or leave the default one.
- Choose a Featured Image.
- Write your post content in the content area.
- Click **Publish** and you're all done.

![Adding New Page](/images/docs/wordpress/bold/adding-new-page.png)

![Create New Page](/images/docs/wordpress/bold/create-new-page.png)

---

### Widgets

The footer section has four registered widget sections. Widgets could be added to these areas by navigating to `Appearance > Widgets`.

![Widgets](/images/docs/wordpress/bold/widgets.png)

![Footer Widgets](/images/docs/wordpress/bold/footer-widgets.png)

---

### Menus

To create a new menu:

1. Navigate to **WordPress Dashboard > Appearance > Menus**
2. You can see a panel where you can create a new menu, click **create a new menu** link to create one.
3. Give the new mene a name, for example, *Primary Menu*, then click the **Create Menu** button to craete it.
2. From the drop-downs on the left, choose the content to add to your menu.
3. Nest & position menu items by dragging & dropping them.
3. Be sure to check the box to set the menu as "Primary Menu" from the **Display location** option.
3. Save menu

![Add New Menu](/images/docs/wordpress/bold/add-new-menu.png)

![Create New Menu](/images/docs/wordpress/bold/create-new-menu.png)

![Edit Menu](/images/docs/wordpress/bold/edit-new-menu.png)

---

You can create a menu as the above steps, with a custom link to the social media site, then you can assign the menu to the `Social Menu` location in the **Display location** option.

![Edit New Social Menu](/images/docs/wordpress/bold/edit-new-menu-social.png)

Bold is using [Social Logos](https://github.com/Automattic/social-logos). You can look this [gallery](https://wpcalypso.wordpress.com/devdocs/design/social-logos) for all the available icons.

---

### Home Hero

![home-hero](/images/docs/wordpress/bold/home-hero.png)

The hero section shows the blog *Tagline* and the *Header Image*.

To set the *Tagline*, go to **Appearance > Customize** then **Site Identity**.

To set the *Header Image*, go to **Appearance > Customize** then **Header Image**.

If the *Header Image* is not exist, the hero section will be hidden, but you can show only the *Header Image* without the *Tagline*.

---

### Contact Page

The first thing you can do is to install and activate the [Contact Form 7](https://wordpress.org/plugins/contact-form-7/) plugin.

#### Creating the Form

- From WordPress Dashboard, navigate to **Contact > Add new**.
- Now you are on the contact form page, set a form title, then and you can see different tabs which are the following:
  - **Form**: You can customize the form and how it will look like with some simple HTML code.
  - **Mail**: You can set direrernt things like you email address and customize the message body.
  - **Messages**: You can set different messages visitors can see in different senarios while sending a message.
  - **Additional Settings**: You can add customization code snippets.
- Once finished the form customization, click the **Save** button.
- Once saved, you will get a new code snippet highlighted in blue. This code will be used with the WordPress page, so please copy it.

#### Creating the Page

- From WordPress Dashboard, create a **Contact** page by navigate to **Pages > Add new**.
- Paste the generated contact form code into the page text box.
- Now, your page is ready with the new contact form which you can then publish.

---

### Galleries

The demo is using the [Tiled Galleries](https://jetpack.com/support/tiled-galleries/) which is a Jetpack add-on that enables to display your galleries in different new styles.

First, install [Jetpack](https://wordpress.org/plugins/jetpack/) and then follow this [guide](https://jetpack.com/support/tiled-galleries/) which will introduce you to Tiled Galleries and how to confugure and create new galleries with it.

---

### Translation

Bold theme is full ready to be translated into other languages and could be easily translated with [poedit.net](https://poedit.net/) application.

The theme contains the main translation file `bold.pot` inside the languages directory which will be used by poedit application.

Here are simple steps:

1. Install poedit and open it.
2. Once the app is opened click Create new translation.
3. Choose the `bold.pot` file inside the theme `bold/language` directory.
4. Once the translation is done, save the file according to your language code. Find a list of language codes at [WordPress in your Language](https://make.wordpress.org/polyglots/teams/). As an example, the language code for English (UK) is `en_GB`, so you will end up with two new files: `en_GB.po` and then `en_GB.mo`.
5. When that’s done, simply upload the files to `bold/language` folder using FTP.
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