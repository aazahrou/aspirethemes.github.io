---
layout: post
title: Push WordPress and Ghost Themes to DigitalOcean with Bash Script
tags: [WordPress, Ghost, DigitalOcean, BashScript]
thumbnail: '/images/posts/digitalocean/digitalocean.png'
---

While we develop themes as developers, we need to test them with a remote server, and this test happens a lot of times a day while working. This requires to move to the themes directory, zip the theme file, login to the server using ssh, then push the zip file to the remote server, then login to WordPress to activate the theme, or in the Ghost case, we need to restart the Ghost server for changes to reflect. All of these processes will take a lot of time and they are boring to do again and again.

I have searched on how I can automate compressing a theme, pushing a theme to a remote server, then I can do anything I want on the server, for example, I can restart the Ghost server so the new changes will reflect, and so on. All of this could be done using a simple Bash script file.

This is the script I did to push a WordPress theme from local machine to a remote server running on DigitalOcean.

{% highlight shell %}
#!/bin/bash

IP_ADDRESS=107.170.4.132
THEMES_DIR=$HOME/www/aspire/wp-content/themes/
REMOTE_THEMES_DIR=/var/www/html/wp-content/themes/

cd $THEMES_DIR
rm -rf aspire.zip
echo '===>> Removed aspire.zip'

zip -r aspire.zip aspire -x *git* *node_modules* *bower_components* *.DS_Store* *.ds_store* *.editorconfig*
echo '===>> Zipped to aspire.zip'

scp $THEMES_DIR/aspire.zip root@$IP_ADDRESS:$REMOTE_THEMES_DIR
echo '===>> Pushed to the server '

ssh -t -t root@$IP_ADDRESS << EOT

cd $REMOTE_THEMES_DIR
rm -rf aspire
echo '===>> Removed aspire'

unzip -o aspire.zip
echo '===>> Un Zipped'

rm -rf aspire.zip
echo '===>> Removed aspire.zip'
echo '===>> Done '

exit 1

EOT
{% endhighlight %}

**To run the script**

From the above script, you have to change some variables:

**IP_ADDRESS**: The droplet IP Address

**THEMES_DIR**: The local WordPress themes directory

**REMOTE_THEMES_DIR**: The remote server WordPress themes directory (this is the default path)

**Theme name**: in my case is *aspire*

The script also does a zip file and ignore some folder and files, for example, it ignores the *git* *node_modules* directories, you may want to edit this line to your needs.

Next, you need to give a permission to the file *aspire.sh*, and then execute the file in the command line.

{% highlight shell %}
chmod +x aspire.sh

./aspire.sh
{% endhighlight %}

### For Ghost Theme

{% highlight shell %}
#!/bin/bash

IP_ADDRESS=162.243.123.249
THEMES_DIR=$HOME/www/ghost/apps/ghost/htdocs/content/themes
REMOTE_THEMES_DIR=/var/www/aspire/content/themes/

cd $THEMES_DIR
rm -rf aspire.zip
echo '===>> Removed aspire.zip'

zip -r aspire.zip aspire -x *node_modules* *git* *.DS_Store* *.ds_store*
echo '===>> Zipped to aspire.zip'

scp aspire.zip root@$IP_ADDRESS:$REMOTE_THEMES_DIR
echo '===>> Pushed to the server '

ssh -t -t root@$IP_ADDRESS << EOT

cd $REMOTE_THEMES_DIR
rm -rf aspire
echo '===>> Removed aspire'

unzip -o aspire.zip
echo '===>> Un Zipped'

rm -rf aspire.zip
echo '===>> Removed aspire.zip'

sudo service aspire restart
echo '===>> Aspire Restarted'
echo '===>> Done '

exit 1

EOT
{% endhighlight %}

This is very similar to the WordPress one, and you will notice that at the bottom we did a server restart. You can give permission to the file, change variables, … as you need.

So, this saves me a lot of time doing repetitive tasks every time I need to update and test a theme. Another point is that this type of script will work with any server that you have access to with ssh, I have tried it with AWS and it worked fine too.

You can try it and let me know what do you think, and if you have any questions or thought for making this script better.