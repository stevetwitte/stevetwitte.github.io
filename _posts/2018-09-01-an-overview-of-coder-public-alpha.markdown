---
layout: post
title:  "An Overview of Coder Public Alpha"
subtitle: "Checking out the public alpha for the new cloud IDE, Coder"
date:   2018-09-01 14:00:00 -0500
categories: development
tags: web tooling development cloud
header_image: "coder-alpha-head.jpg"
---
Coder is a web-based IDE with the standout feature of giving you a scalable container, with full root access, to run your code.  The cloud IDE has entered public alpha, and I was curious to see how well it performed and what, if any, were its shortcomings.  This article is by no means a comprehensive review just an overview of my time with the Coder public alpha.

![Coder Alpha](../assets/coder-image-1.png)
 
### Highlights from the Homepage

Scrolling through Coder's homepage describes a cloud IDE with full support for 15 languages including C, C++, Java, HTML, Javascript, Typescript, PHP, Ruby, and more.  They also list 9 partially supported languages but there is no mention of what that means, but it's safe to assume those are still in development as this is alpha code.

The homepage also mentions the ability to create shared workspaces, real-time collaboration, a feature called Fast Time that will be covered later, the ability to work on any device and their "supreme security."  It's easy to see why a lot of people would be interested in something like this, so let's see what it's like to work in a cloud IDE.

 
### Spinning up a Project

After signing up with either email or a GitHub account, we are taken to the Dashboard.  Here you have access to all your projects and containers, more on those later, and to the left, you can switch to your control panel, view documentation and redeem a fast time code.

After creating a project, you can open the IDE.  Doing this brings your container online and loads the IDE/editor with a base directory at /coder/mnt/your-user-name/project-name, and here you are pretty much left to do whatever you want.

You are presented with an IDE that has project-wide search, autocomplete, and a full terminal with root access.  I develop mostly in Ruby on Rails and React, and they both have pretty self-contained installers/setups so I figured I would see if I could spin up a new Rails app and if I could run create-react-app successfully.

![Coder Alpha](../assets/coder-image-2.png)
 
### Are the Rails on?

Switching over to the terminal view brings up a bash prompt at the project root, where you can see that you are logged in as the root user.  I tried checking the Ruby version on the machine, it wasn't installed, so a quick check on the documentation showed that once you create a ".rb" file, Ruby would install.  

All right we have Ruby installed and now on to Rails.  Gem install rails gave me a couple of errors.  It looks like I need to install some dependencies first.  Running "apt-get update && apt-get install -y build-essential locales nodejs" seemed to get me closer and I was able to install Rails, but when running rails new AppName I got an error installing the SQLite gem.

Upon closer inspection, it seems to be an issue with the GCC compiler.  I was about to start debugging this issue when I decided to leave it alone.  I am not interested in developing with SQLite in the real world, so I decided to call it.  I was able to run a file through the ruby command line and get output so my conclusion here is that Ruby works but something with as many dependencies as Rails may or may not work and probably will require some particular config.

 
### Create a React App?

I created a new project, ran "npm install -g create-react-app," and it installed with no issues.  Running "create-react-app test-app" was successful as well, with no errors or warnings in site.

Starting the development server was the usual "npm start," but to see the result, you use their method for connecting from another browser window to your server.  This window works with live-reload and even includes https for an experience much like a paid NGROK account.  I was surprised that everything here works as expected with no significant differences to the way I would start a new React project locally.

![Coder Alpha](../assets/coder-image-3.png)

### How does it feel?

The overall feel of typing into Coder was very similar to what you would expect when SSH'ing onto a remote server.  My internet connect is 100mbps down, and I experienced a small amount of lag, I could certainly tell I was not working on my local machine, but nothing that would keep me from getting things done.

The IDE feels and looks a lot like Visual Studio Code does out of the box.  I wouldn't put it on par with what we would call an IDE in the desktop world.  It's very capable but seems more like an editor with the usual plugins installed.  For example, I would expect an IDE to know if I was using a class without importing it, this didn't recognize the error.

 
### What is Fast Time?

Fast Time is a paid upgrade billed at an hourly rate and "dynamically scales your container up to 96 cores."  They don't go into any more detail other than how to purchase Fast Time, but since I got 5 hours of it for free, I activated it during the Rails install.  Activating this brought my CPU usage down considerable and I am sure sped things up but more in-depth testing is needed to confirm what exactly is going on.

 
### Conclusions

I have only scratched the surface of the languages available, and more are coming soon, as this is Alpha, but overall I think that the team at Coder is onto some really cool stuff.  I am very impressed with all that you can do at this early stage and am looking forward to the future of this company and the whole concept in general.  We have already moved so much of what we do to the cloud it makes sense that we would start editing there as well.
