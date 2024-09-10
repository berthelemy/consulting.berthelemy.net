---
title: Securing Wordpress
author: Mark Berthelemy
excerpt:
 As one of the most popular web content management systems, Wordpress is also one of the most vulnerable to attack. Find out three ways to help keep your site secure.
layout: post
permalink: /2016/04/18/securing-wordpress
tags:
  - Content management
  - Project management
thumb: /post-images/2016/04/securing-wordpress-thumb.png
banner: /post-images/2016/04/securing-wordpress-banner.png
alt: Wordpress logo with padlock
img-credit: Wordpress &amp; Pixabay
---
Wordpress is at the heart of many thousands of websites around the world. Just by virtue of its popularity it&rsquo;s become vulnerable to attack. That doesn't mean that Wordpress is insecure. It's just that sometimes organisations run it in an insecure way.

I would like to propose three sets of actions, which, when put together, will make a strong defence for any Wordpress site:

#### Policies and practices

1. Keep the number of people with admin rights to a bare minimum. Ideally have just two administrator logins (so that one can be used if you lose the password for the first).
2. Don't use an administrator login for general use, eg. writing posts and editing pages.
3. Never share usernames or passwords between people. You'll want to be able to audit who did what.
4. Only select plugins and themes that have been tested with your version of Wordpress, have been updated within the last few weeks, and have a solid number of happy users.
5. Ensure your files and data are backed up regularly (the frequency will depend on how often things change, but weekly would be a minimum) - and know how to restore them if the worst should happen. There are plugins, like <a href="https://www.akeebabackup.com/products/akeeba-backup-wordpress.html" target="_blank">Akeeba Backup</a>, that can help with this.
6. Ensure your plugins and themes, and the Wordpress core code is updated immediately new versions are released. The <a href="https://www.wordfence.com/" target="_blank">Wordfence</a> plugin will email you whenever there's something to update.
7. Use strong passwords, and store them securely - eg. with a password vault such as <a href="https://lastpass.com/" target="_blank">LastPass</a>.

#### Hardening

1. Change any default usernames or passwords to something new. This applies to Wordpress, to the Database, and to your FTP user.
2. Make sure your database user cannot access other databases - and especially isn't the root user.
3. Consider restricting access to the Admin dashboard from known IP addresses (although this may not be practical if people are moving around a lot).
4. Use a plugin such as <a href="https://wordpress.org/plugins/rename-wp-login/" target="_blank">Rename WP login</a> to change the URL of the login page
5. Only get plugins and themes from known sources, such as the Wordpress repository.
6. Remove any plugins or themes that you are not using.

#### Monitoring

1. Use a plugin like <a href="https://www.wordfence.com/" target="_blank">Wordfence</a> to keep an eye on your site. It provides a number of tools to check for strange activity and changes in the code. You will need to get a little bit technical to interpret whether the warnings it gives can be ignored safely.
2. Set up a regular monitor to see whether your site is behaving properly. There are <a href="https://www.google.co.uk/search?q=website+monitoring" target="_blank">many services</a> that do this, some free. The paid for ones will offer more frequent monitoring, and usually a better user interface. Most will give you a free trial period.
3. Consider using a plugin like <a href="https://wordpress.org/plugins/enhanced-plugin-admin/" target="_blank">Enhanced Plugin Admin</a> which will show at a glance which of your plugins may be out-of-date.
