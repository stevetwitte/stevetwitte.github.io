---
title: 'The Story of a Rails MVP'
description: 'I recently had a great experience ditching the hassle of an API/Client app situation in favor of a standard Rails web app.  Here is the story of finding the path of least resistance with MyInvestmentTime.com.'
pubDate: 'Aug 25 2018'
heroImage: '/mvp-hero.jpeg'
---
I recently had a great experience ditching the hassle of an API/Client app situation in favor of a standard Rails web app.  Here is the story of finding the path of least resistance with MyInvestmentTime.com.


Some time ago I was sitting at my desk on a Friday, I had finished my sprint and was looking at a full day of investment time but had no idea what to tackle.  The thought popped into my head that there might be a website or forum where I could get some inspiration.  I thought there would have already been a site where people talked about investment time.  It turns out that site does not exist, at least as far as I can tell, and so I decided to create MyInvestmentTime.com.

## The Idea
The idea was to give users a Twitter-like feed to check on what the community was doing in their investment time.  I soon thought of my team and wanted to add a way to track teams and to update the status of the task or project.  I have tried to be careful in not creating a replacement for typical project management tools.  I don't want to replace GitHub or Trello.  So instead think of MyInvestmentTime.com as a standup for your investment time and a way to share that among teams and the broader community.

## The Path
I started as a Ruby on Rails developer, and at my company, we generally go with a Rails API back-end and Angular front-end.  That seemed like a logical starting point for my app as well, but I already knew Angular and because this was a fun side project I decided to go with something new.

Around this time Create React App had just been released.  It seemed like a perfect time to learn React, so I decided to go with a Rails API back-end and a React front-end.  I worked on this for a few months, on the weekends with a friend who was also learning React and had a very basic working app.

It allowed you to create an Investment and it allowed you to view a feed of other's Investments.  You could log in, sign up and the like but nothing else.  Moreover, as many projects do, this one fell by the wayside when work picked up for me.  So the Heroku app sat there, and the repos didn't get any commits, and my URL still pointed to nothing.

## A Quicker Path
A month ago I was sitting in my kitchen, checking on my RSS feeds, I had a little more free time and thought that it might be nice to check out the long-lost app and get some work done.  A lot had changed in my personal views on delivering code and working from idea to MVP and after seeing the code, and what it was doing I realized that a lot was going on and achieving very little.

There didn't seem to be any reason this app shouldn't just be server-side rendered, at least for most of the time.  Rails 5.1 was released since I started, which opened up the possibility of adding React components were they needed for real-time functionality, or maybe at this point, I would go with Vue.js, but it seemed silly to have a client and API setup for something as simple as this.

I decided that I would start with a base Rails app and I would use every tool out there to make development more comfortable and quicker.  It turns out that with a few gems I was able to get the first full MVP done in four days at around 5 hours a day.

## Structure
I started with a "rails new" on version 5.2 and began creating.  The structure of the app is straightforward, and there is a link to the repo at the bottom of the article if you want to check it out.  Here are some highlights.

I used Clearance <a href='https://github.com/thoughtbot/clearance'/>(https://github.com/thoughtbot/clearance)</a> for authentication which gave me a real headstart.  The gem is not as famous or prominent as Devise, but I prefer it's customization and it still gives you everything you need out of the box.  I used it's generators to give me a user model and all my basic views.  I then sub-classed their controllers for a simple change to add a username to signup and defined my routes.  The only thing left was styling.

CanCanCan <a href='https://github.com/CanCanCommunity/cancancan'/>(https://github.com/CanCanCommunity/cancancan)</a>  was another great addition and helped to clean up my controllers and simplify them a great deal.  It is an authorization and resource loading library that works of the concept of abilities.  You define a set of abilities for your user, separated by model, type, role.  Then in your controller, you can authorize and load that resource automatically with one before action.  My explanation is an extreme oversimplification of what the gem can do, and I encourage you to read one of the many excellent tutorials or just the wiki for CanCanCan, which is also very informative.

I am not a designer, and while the site is functional, I don't think it is going to win any awards just yet.  TailwindCSS <a href='https://github.com/tailwindcss/tailwindcss'>(https://github.com/tailwindcss/tailwindcss)</a> did give me the ability to design in the browser with much more flexibility and speed then I am usually accustomed too.  It allows you to focus on the structure of your site with no opinion on how it should look.  I like it, and it has the tools you need to extract those HTML elements into classes.  It uses PostCSS and Javascript, so I integrated it using web pack in Rails.

These tools along with the Rails framework, in general, allowed me to deliver a very clean code base with a minimum number of dependencies and a very polished experience.  Testing with RSpec for everything from Unit to View was a breeze.  Model validations carry over to forms automatically and so much more.  A lot of which I would have had to build from scratch or download a library for in the API/SPA world.

## Conclusion
There are many times where this project setup does not make sense.   One of the big reasons we go with an API/Client design is because there are multiple clients that all need access to the same data.  I could see a need for more real-time functionality in many apps or the situation where a client needs to talk to many microservices directly.

There are many other reasons to not go with a monolith Rails app but none of them applied to my project, and I bet a lot of them don't apply to your project either.  I was extremely impressed by how little code I had to write apart from the HTML.  It boiled down to config and setup more than anything else.

So next time you are starting a new project avoid the temptation to reach for the new shiny thing and look at some of the tried and true options.  You may be impressed by what years of development and support can do to a framework or library.

<a href='https://github.com/stevetwitte/my-investment-time'>https://github.com/stevetwitte/my-investment-time</a>
