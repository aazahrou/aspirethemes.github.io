---
layout: post
title: How to Add Social Media Links to Your Moodle Theme
tags: [moodle, social-media, theme]
thumbnail: '/images/posts/moodle-social/cover.jpg'
---

Adding social media links to your Moodle site is something that will make it easier for students and visitors to easily follow, interact and find more information about your organization.

In this post, I will share with you how you can integrate the social media settings functionality that will enable you to add the links from the Moodle admin and then show them in the Moodle theme, in this case, the Boost default theme, but the code and the concept would work with any theme and I chose Boost as it's the default and the standard one comes with Moodle.

I will add the link settings to Facebook and Twitter, but adding any other social media links would follow the same structure.

We need to do 4 steps to make this happen:

1. Add Translation Strings for Settings Labels
2. Add Admin Settings for Adding the Links
3. Set Up Links Mustache Template Helpers
4. Show the Links Within the Theme Template File

### Add Translation Strings for Settings Labels

Let's start with the translation strings for labels by adding the following code example to the `lang/en/theme_boost.php` file.

```php
// Social Media Settings
$string['social_media_settings'] = 'Social Media Settings';

// Facebook
$string['facebook_link'] = 'Facebook Link';
$string['facebook_link_desc'] = 'Enter your Facebook page link';

// Twitter
$string['twitter_link'] = 'Twitter Link';
$string['twitter_link_desc'] = 'Enter your Twitter page link';
```

The first string is for the admin setting tab and then for each social link, we add a label string and a description text to provide more information about that field.

### Add Admin Settings for Adding the Links

Next, we will add the admin setting section which will be used to add and edit the social media links. Open the `settings.php` file and add the following code:

```php
// Social Media Settings
$page = new admin_settingpage('theme_boost_social_media_settings', get_string('social_media_settings', 'theme_boost'));

// Facebook
$name = 'theme_boost/facebook_link';
$title = get_string('facebook_link', 'theme_boost');
$description = get_string('facebook_link_desc', 'theme_boost');
$default = '';
$setting = new admin_setting_configtext($name, $title, $description, $default);
$page->add($setting);

// Twitter
$name = 'theme_boost/twitter_link';
$title = get_string('twitter_link', 'theme_boost');
$description = get_string('twitter_link_desc', 'theme_boost');
$default = '';
$setting = new admin_setting_configtext($name, $title, $description, $default);
$page->add($setting);
$settings->add($page);
```

This will create a new setting tab called **Social Media Settings** with two text fields for Facebook and Twitter. You can see the result now by going to *Site administration > Appearance > Themes* and click the Boost theme from the themes list, then you will be redirected to the theme settings page where you can see the newly created tab, click it and you see the settings section as follows:

![Moodle Social Media Settings Tab](/images/posts/moodle-social/moodle-social-media-settings-tab.png)

Now, try to fill up the fields with your current links and click *Save changes* button, it then will save them into the database and show them directly into the fields once the pages reload.

![Moodle Social Media Settings Tab Saved](/images/posts/moodle-social/moodle-social-media-settings-tab-saved.png)

After making sure that all links are saved and work as expected, it's time to show these in front of people and this is what we will do in the next step.

### Set Up Links Mustache Template Helpers

I want to make it easier to embed these links in a mustache template, for example, `columns2.mustache` which is the main layout for the Boost theme, so I decided to get the links and pass them as context variables in the `columns2.php` layout file. By doing this, we can output a link using something like `{{facebook_link}}` and also we can check if it is empty or not, this gave more control for the output result.

Open the `columns2.php` layout file and paste the following code before the `$templatecontext` variable.

```php
// Social Media Links
$theme_config = theme_config::load('boost');

$facebook_link = $theme_config->settings->facebook_link;
$twitter_link = $theme_config->settings->twitter_link;
```

Next, inside the `$templatecontext` array, we can add the contexts for both Facebook and Twitter links as:

```php
$templatecontext = [
    // Other exciting code here ...

    'facebook_link' => $facebook_link,
    'twitter_link' => $twitter_link
];
```

### Show the Links Within the Theme File (Footer)

Now, if you opened the `columns2.mustache` file and added `{{facebook_link}}` or `{{link_link}}` in the footer, for example, you will see the links output to the screen.

We can also check if any of the links exist or not before putting the link, this will enable us to generate more customized content like doing the following:

```html
{% raw %}{{# facebook_link }}{% endraw %}
  <a href="{% raw %}{{facebook_link}}{% endraw %}">Facebook</a>
{% raw %}{{/ facebook_link }}{% endraw %}

{% raw %}{{# twitter_link }}{% endraw %}
  <a href="{% raw %}{{twitter_url}}{% endraw %}">Twitter</a>
{% raw %}{{/ twitter_link }}{% endraw %}
```

I have created [GitHub repository](https://github.com/aspirethemes/boost) with all the code implemented to the Boost theme and every step is added into a [seperated commits](https://github.com/aspirethemes/boost/commits/master) so you can follow up and make sure that everything is on the right place.

Hopefully, this post helps you with social media integration for your website and of course I would be happy to hear your feedback and if you have an alternative way that you want to share in the comments below.