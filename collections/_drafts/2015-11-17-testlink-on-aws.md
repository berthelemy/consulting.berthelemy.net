---
title: 'Installing Testlink on Amazon Web Services'
author: Mark Berthelemy
excerpt:
 How to setup the Testlink test management system within Amazon Web Services
layout: post
permalink: /2015/11/17/testlink-on-aws
tags:
 - Technology
thumb: /post-images/2015/11/testlink-logo.png
banner: /post-images/2015/11/testlink-on-aws-banner.png
alt: Testlink
img-credit: Testlink and Amazon
---
I have been using <a href="http://testlink.org" target="_blank">Testlink</a> on and off for a number of years as a tool to help define and execute tests against all sorts of software. It&rsquo;s far better than trying to track everything on spreadsheets (see my recent post on <a href="/2015/11/10/making-content-better">Making Content Better</a> for a bit more rationale).

I needed to move my Testlink installation from my shared web-server to something a bit more robust and scalable, and have chosen <a href="https://aws.amazon.com">Amazon Web Services (AWS)</a> given its reputation and my previous experiences with some rather large clients of their&rsquo;s.

Setting up Testlink on the server was mostly quite straightforward, but there were a few places where I ended up scratching my heads. Hopefully this brief set of instructions will help others in the same position!

1. Create an account on <a href="https://aws.amazon.com">Amazon Web Services (AWS)</a>. You will need to put in payment details, but that doesn't mean you'll be charged anything just yet. We'd suggest just signing up for the free, basic level at this stage.
2. Go to the AWS console
2. Change your required server location (next to your name at the top right) to meet your needs. I chose "Ireland".
2. Begin the process of launching an EC2 instance... That sounds complicated but it&rsquo; simply a matter of hitting the "Launch Instance" button from the AWS console. The process is almost identical to that of <a href="https://aws.amazon.com/getting-started/launch-a-wordpress-website/" target="_blank">launching a Wordpress site on AWS</a>
3. In the tabs on the left-hand-side, choose AWS Marketplace
4. Within the Marketplace, search for "Testlink". It will bring up a list of 2 or 3 different Bitnami packages to use.
5. I chose the package that uses Bitnami (HVM) as it gave me the right selection of server sizes for my needs. You might need to experiment to see which version gives the server you need.
6. You will be asked to choose an <a href="https://aws.amazon.com/ec2/instance-types/" target="_blank">Instance Type</a>. This is where you'll need to do some thinking, and may need to go back to the previous step to choose a different Bitnami package. Amazon do give you the option of choosing a free instance (free for one year), but this is very small and probably not suited to any more than a "getting started" setup. Testlink recommend going for the m3.medium instance - but that may be overkill for some. If you&rsquo;re not sure, that&rsquo;s where we'd probably recommend bringing in someone who knows AWS to provide some support.
7. AWS gives you options to configure the instance, but you can just use the defaults provided by Bitnami and hit "Review and Launch"
8. Don't forget to <a href="http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#having-ec2-create-your-key-pair" target="_blank">create and download the .pem private key file</a> (and save it somewhere you can get to). The launch process will guide you through how to do this. You will need this when connecting to the server to configure Testlink.

If you then go to the IP address supplied by AWS, you should see the Testlink login page. However, the normal Bitnami password doesn't seem to work, so you'll need to change it, but you'll only be able to do that when you've got a way for Testlink to send emails...

#### Setting up an AWS SMTP server

There are three stages to getting Testlink setup so it can send emails:

##### Verify email addresses

Setup verified email addresses (ie. those which you&rsquo;ll be using within Testlink) within Amazon's Simple Email Service (note this route is only suitable for small teams, for larger teams you'll need to <a href="http://docs.aws.amazon.com/ses/latest/DeveloperGuide/request-production-access.html" target="_blank">ask Amazon for production access</a>)

##### Obtain your Simple Email Service SMTP credentials

<a href="https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html" target="_blank">Obtain SES credentials</a> so that Testlink can use SES

##### Configure Testlink to use SES

This is where you'll need to <a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html" target="_blank">connect to the AWS server via SSH</a>, using the .pem file created earlier. Note that AWS helpfully provides a connect button on the EC2 > Instances page, with commands for your particular instance.

<img class="aligncenter" src="/post-images/2015/11/connect-to-instance.png" alt="AWS Connect button" />

Once you've connected using SSH, you can edit the /apps/testlink/htdocs/custom_config.inc.php file (I tend to use the nano editor, but you can also use vi if you like esoteric editing commands).

Find the section headed SMTP server configuration, and then add in the following details (NB. These are taken from the <a href="https://www.mantisbt.org/" target="_blank">Mantis Bug Tracker</a> configuration - which is copied by Testlink - <a href="https://www.sankaranand.com/blog/2012/09/configuring-amazon-ses-with-mantis-bug-tracker-for-email-notifications/" target="_blank">see this forum post</a>)

    define ("SMTP_SEND", 2);
    $g_phpMailer_method = SMTP_SEND;  #For SMTP Method
    $g_smtp_host = ‘email-smtp.us-east-1.amazonaws.com'; #Your SES SMTP Host
    $g_smtp_connection_mode = ‘tls'; #It is mandatory for SES and Gmail SMTP
    $g_smtp_port = 587; #For some Reason only this port was working in SES
    $g_smtp_username = ‘SMTP Username'; # Your SES SMTP Username (a 20 character string)
    $g_smtp_password = ‘SMTP Password'; # Your SES SMTP Password
    $g_tl_admin_email = ‘email@sample.com'; #Email displayed at footer (Must be an approved sender list in SES)
    $g_from_email = ‘email@sample.com'; # From Address (Verified SES Sender Email)
    $g_return_path_email = ‘email@sample.com'; # the return address for bounced mail
    $g_from_name = ‘From Name';
    $g_enable_email_notification = ON;


Once all that is done, you should have a working Testlink installation. It may need further tweaks, but check out the documentation stored inside the docs directory.

Note: If you want to access PHPmyadmin to administer the database, create an SSH tunnel to the port 80 instead. This can be done as follows in Unix systems:

    ssh -i <path_to_private_key> -N -L 8888:127.0.0.1:80 <public_dns>

or with Putty on Windows using source port 8888 and destination 127.0.0.1:80.

Once done it will be accessible at http://localhost:8888/phpmyadmin while the tunnel is opened. Credit to <a href="https://bitnami.com/forums/forums/bitnami-cloud/topics/can-t-access-phpmyadmin#post_10627" target="_blank">Carlos on the Bitnami forums</a> for this advice.
