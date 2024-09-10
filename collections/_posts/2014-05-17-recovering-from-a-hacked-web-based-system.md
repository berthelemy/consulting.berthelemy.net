---
title: Recovering from a hacked web-based system
author: Wyver Solutions Admin
excerpt: "Following a recent spate of attacks on commonly-used web applications, I discuss how to recover from an attack, and how to try to ensure it doesn't happen again."
layout: post
permalink: /2014/05/17/recovering-from-a-hacked-web-based-system/
tags:
 - Project management

---
Following on from my past two posts about [risk][2] and [security][3], it&#8217;s probably a good idea to identify a few techniques which might help you to recover your systems following an attack.

Remember that most attacks succeed on systems that haven&#8217;t been kept up-to-date. You can mitigate a lot of risk just by ensuring you have the most recent version of the software installed on your servers (assuming you&#8217;re using software that gets updated regularly).

## Spate of attacks

There are a lot of attacks taking place at the moment on popular open-source applications like [WordPress][4] and [B2evolution][5]. L&amp;D teams across the world are starting to embrace these types of easy-to-use content management systems. They are extremely simple to install, and also to modify &#8211; using plugins, with very little technical expertise required.

But this simplicity makes them vulnerable. Administrators will need to ensure that the modifications they make, as well as the core system, are maintained. If you have an old WordPress installation, that&#8217;s no longer used, but is sitting on the same server as your other systems, then that puts everything at risk.

## How do you know you&#8217;ve been hacked?

The most usual means to find out that your system has been attacked are:

  1. A message from your friendly web-hosting service, which has detected something odd &#8211; often through their anti-virus programme
  2. A message from a friend who&#8217;s seen odd behaviour on your site &#8211; perhaps strange messages, a virus warning in their browser, or even the wrong site being displayed
  3. A message from [Google&#8217;s webmaster tools][6] warning that you&#8217;ve been hacked. (You will need to register your site with Google to take advantage of this.)

If Google or your web-host are involved, they should hopefully be able to give you some pointers as to what type of attack you&#8217;ve suffered. Two typical ones are:

  * URL injection &#8211; where your URL takes people to another, malicious site. If this happens, check your .htaccess file for strange entries, as it&#8217;s the most probable location of the redirection code.
  * Code injection &#8211; where the attacker has managed to place malicious code into your files. To fix this will involve considerable analysis to find the hacked files, which code has been placed there, and to remove it.

Both of those situations can be resolved by finding the appropriate bits of code and clearing them out. If a lot of files are involved, then it&#8217;s possible to write a &#8220;script&#8221; that runs through and checks each file in turn. But take care that you don&#8217;t cause more damage than the original attacker!

If a hacker has chosen to damage your files or your database, as well as add code to it, then the usual way to recover is to restore from a recent backup &#8211; losing everything that has been saved in the meantime.

Once you&#8217;ve recovered your system, then you will need to spend some time trying to ensure that the attacker can&#8217;t get back in again. This will involve:

  1. Changing all administrator passwords
  2. Upgrading your system, and plugins, to the most recent version
  3. Clearing out old applications that are no longer used
  4. Clearing out old plugins that have not been updated for a while

&nbsp;

[2]: {{ site.url }}/2014/03/26/weighing-up-the-risks-a-sensible-attitude-to-security/ "Weighing up the risks: a sensible attitude to security"
 [3]: {{ site.url }}/2014/05/08/who-is-responsible-for-security/ "Who is responsible for security?"
 [4]: http://wordpress.org/
 [5]: http://b2evolution.net/
 [6]: https://www.google.com/webmasters/tools
