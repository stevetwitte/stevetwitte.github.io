---
title: "From Vim to VS Code"
description: "The story of a Vim/Neovim lover and their move to Visual Studio Code"
pubDate: "Aug 28 2023"
heroImage: "/mvp-hero.jpeg"
---

I decided that I would start with a base Rails app and I would use every tool out there to make development more comfortable and quicker. It turns out that with a few gems I was able to get the first full MVP done in four days at around 5 hours a day.

## Structure

I started with a "rails new" on version 5.2 and began creating. The structure of the app is straightforward, and there is a link to the repo at the bottom of the article if you want to check it out. Here are some highlights.

I used Clearance <a href='https://github.com/thoughtbot/clearance'/>(https://github.com/thoughtbot/clearance)</a> for authentication which gave me a real headstart. The gem is not as famous or prominent as Devise, but I prefer it's customization and it still gives you everything you need out of the box. I used it's generators to give me a user model and all my basic views. I then sub-classed their controllers for a simple change to add a username to signup and defined my routes. The only thing left was styling.
