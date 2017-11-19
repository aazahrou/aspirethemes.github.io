---
layout: post
title: How to Add a Contact Form to Your Ghost Blog
tags: [Ghost, contact]
thumbnail: '/images/posts/ghost-contact/cover.jpg'
description: In this post, I will go through adding a contact form, from creating the contact page, add the form, and then add the page to the site navigation.
---

Recently, one of my customers at [Aspire Themes](https://aspirethemes.com/?utm_source=medium&utm_medium=articles) asked me if there is a way to add a contact form the his new Ghost blog as there is no built in contact form shipped with Ghost and there is no support for plugins like WordPress for example.

I did some research and found some interesting tools to add a contact form quickly to Ghost. I found [Formspree](https://formspree.io/) to be a great and quick option to try and it is also free to use.

In this post, I will go through adding a contact form, from creating the contact page, add the form, and then add the page to the site navigation.

#### Create the Contact Page

From the Ghost admin, click **New Story** button, add the post title, and then click the **Turn this post into a static page** option.

<figure markdown='1'>
![Create the Contact Page](/images/posts/ghost-contact/contact-page.png)
<figcaption>Create the Contact Page</figcaption>
</figure>

Once this is done, we can now move to the next step.

#### Create the Contact Form

The following code is a simple example, which contains the name, email, and a text area fields, which the sender can fill and send the message.

```html
<form action="https://formspree.io/your@email.com" method="POST">
  <input type="text" name="name">
  <input type="email" name="_replyto">
  <textarea name='message'>  </textarea>
  <input type="submit" value="Send">
</form>
```

The required thing to do is to replace the email with your own email address, copy the code to the page content, then you can **publish** the page.

![Form Code](/images/posts/ghost-contact/form-code.png)

Now, go to the contact page and submit the form once. This is a required step and you will get an email asking you to confirm your email address.

Once you confirmed your email address, the form will be ready for work and you will get an email once any one sends you an email like the following one.

<figure markdown='1'>
![Message Example](/images/posts/ghost-contact/message.png)
<figcaption>Message Example</figcaption>
</figure>

#### Add the Page to the Blog Navigation

The last step is to add the contact page to the blog navigation. Go to Design > Navigation and a new navigation field with a label and the page slug, then click the **SAVE** button.

<figure markdown='1'>
![form-code](/images/posts/ghost-contact/nav.png)
<figcaption>Message Example</figcaption>
</figure>

You can then style your form based on your design and add more fields or customize the form based on your requirements, so make sure to visit [Formspree](https://formspree.io/) website for more information.

Thank you!