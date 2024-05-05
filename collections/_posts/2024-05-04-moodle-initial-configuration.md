---
title: 'Moodle initial configuration'
author: Mark Berthelemy
excerpt: What do you do to get Moodle ready once it's installed?  
layout: post
datatable: false
tablePagination: false
order: 1
tableRowgroup: 1
permalink: /2024/05/04/moodle-initial-configuration
img: 2024/man-2562325_1280.jpg
imgalt: Man writing next to a laptop
imgcredit: Stocksnap on Pixabay
imgurl: https://pixabay.com/photos/man-writing-laptop-computer-write-2562325/
tags:
  - Solutions architecture
  - Moodle
  - Information architecture
---
I'm assuming you've got a Moodle site installed.

If not, then you'll need to choose one of these options:

- Create a site at [Moodlecloud](https://www.moodlecloud.com/){:target="blank"}
- Work with a specialist Moodle hosting supplier (let me know if you need a recommendation)
- [Install a new instance](https://docs.moodle.org/404/en/Installing_Moodle){:target="blank"} on a server of your choice

Your choice will depend on how much you'll need to customize it, your access to technically confident people, and the size and complexity of your target audience.

So, now you have a site setup, what do you do?

Out of the box, Moodle works OK, but there are some things I nearly always do as part of the initial configuration, to make it even better.

As the administrator, you have a duty of care towards your users to keep the site safe, secure and as easy to use as possible.

<blockquote><p>Note: Since Moodle 4.0, the [Admin Presets plugin](https://moodle.org/plugins/block_admin_presets){:target="blank"} has been integrated into the core Moodle code. This allows you to take a copy of your current configuration and import it into another Moodle site. This is such a time-saver if you're setting up multiple Moodle installations. If you're new to Moodle, you might just want to use the provided <mark>Starter</mark> preset and then take a look at the rest of this article.</p>

<p>I'd advise against using Admin presets you've downloaded from elsewhere, unless you really trust the source.</p></blockquote>

## Changing the default settings

For privacy and simplicity at first, I tend to change the following settings from their default:

### Admin > General > Advanced features

Turn these on when you understand what they do and how they work, and you know that you really need them. 

- Comments: Off
- Tags: Off
- Notes: Off
- Blogs: Off
- Badges: Off
- Competencies: Off
- Messaging: Off
- Moodlenet: Off

### Admin > General > Security > Site security settings

- Force users to login to view user pictures: Off
- Maximum uploaded file size: Set this to less than 10MB, to avoid the site becoming bloated
- Cron password for remote access: Set a password
- Password policy: change to your organisation's policy (or see the current guidance from the [National Cyber Security Centre](https://www.ncsc.gov.uk/collection/passwords){:target="blank"}

### Admin > Users > Accounts > User default preferences

- Email visibility: Hidden

### Admin > Plugins > Activities > Manage activities

- Disable the activities that are unlikely to be used in your context (eg. Surveys, Workshop)

### Admin > Plugins > Blocks > Manage blocks

- Disable the blocks that aren't relevant to your learners, or may cause privacy issues (eg. Flickr, Mentees, Network servers, Online users)

### Admin > Plugins > Text editors > Manage editors

- Make sure the TinyMCE editor is on, and Atto and the TinyMCE legacy editors are off. Atto creates unnecessarily dirty HTML.

Once you've done all that, then you can get on with configuring the rest of the site - things like the theme pack, custom css, and category/course structure. 

## Additional resources

If you are completely new to Moodle, then there are heaps of free resources.

Start with the [Moodle Academy](https://moodle.academy/){:target="_blank"}

Refer to the [Moodle administrator documentation](https://docs.moodle.org/en/Managing_a_Moodle_site){:target="_blank"}

Or buy a recent book, such as [Moodle 4 administration](https://www.packtpub.com/product/moodle-4-administration-fourth-edition/9781801816724) by Alex Büchner from Packt Publishing.

Or get someone like me to help set things up and provide coaching and ongoing support.






