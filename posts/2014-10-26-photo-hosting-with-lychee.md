---
layout: post
title: Photo Hosting with Lychee
---
# Introduction

Since I started taking pictures, I haven't had a great place to keep them and share them with the world.  I post a lot of my stuff to Facebook, but overall that lacks a certain public / generic access feel to it.  When you want to share pictures to people on Facebook, they kind of need to be logged in to Facebook.  Not everybody wants to do that, and I find myself pulling back from the great social media monster too, so I want to move to something more mature.

Why not use a paid hosting service to do this?  There are lots of great places to keep your images for the right price.  What if you want something more custom than that?  What if you enjoy the feeling of knowing that you're responsible for securing your own data?  Look no further than Lychee.

# Welcome, Lychee

Lychee is a custom photo management application that's intended to run in a LAMP stack.  It lets you operate a public / private photo album space on your own server, and it supports all of the handy modern features that you'd want in a photo hosting application.  You can check out the feature set on the [Lychee home page](http://lychee.electerious.com/).

# Pixels awash on the DigitalOcean

You need somewhere to run Lychee, and when I need a static server resource, I turn to [DigitalOcean](https://www.digitalocean.com/).  Great interface, great service, right price.  It's $5.00 a month to run a 20GB SSD-backed server with 1 cpu and 512mb of ram, plenty of power for my purposes.  An additional awesome point for DO is that they offer a push-button LAMP stack.  Just select it from the "Applications" tab when launching your instance.

# Installing Lychee

1. **Make it rain.** 

    Kick off a Droplet with 1 CPU and 512 MB of RAM.  I chose to use the built in LAMP package that was offered, which is based on Ubuntu 14.04.

2. **Don't sweat the small stuff.** 

    MySQL, PHP, and Apache are all set up for you on this in advance.  All of the batteries are included, so you don't need to fiddle with php extensions. Log in with SSH and get yourself situated.  
    
3. **Set up your DB.** 

    Log in to the database server with `mysql -p` (using the password that was shown in the motd when you logged in).  
    
    - Create a new user (lychee) and a new database (also called lychee).  
    - Grant all privileges to the lychee database to the lychee user.  
    - Disconnect from the database, then run `mysql_secure_installation` to secure it.
    
4. **Send in the clones.**

    In your browser, go to the [Lychee GitHub page](https://github.com/electerious/Lychee) and in your SSH session, navigate to `/var/www/html/`.  Clone the git into the folder.  **Note:** this creates a `Lychee` directory, so your path to the application would look like `http://<yourdomain>/Lychee`.  If you want to run this without the `/Lychee` path, move the contents of the folder up to the root html directory.  You could theoretically change the folder name to `/photos` or `/images` if you so choose. 
    
    There are some configuration parameters for PHP that you'll want to get from the [installation instructions page.](https://github.com/electerious/Lychee/blob/master/docs/Installation.md)
    
5. **Fire it up.** Use your browser to navigate to your server. If you did the default installation, you'll be going to `http://<yourdomain>/Lychee`.  You'll be prompted for DB credentials, so use the stuff you set up in step 3.  After you complete the dialog, you must log in to Lychee and set up a user credential.  Click the "Login" button in the upper left hand corner, then enter the DB credentials you used for the Lychee user.  You should then be prompted for user credentials for the standard user.

Now you're ready to start uploading images from Dropbox, using the browser, or optionally syncing from a directory on the server (ideal for uploading with SSH).  I'll write more about my experience with Lychee in future posts!
