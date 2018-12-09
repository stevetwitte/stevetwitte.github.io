---
layout: post
title:  "Middleman & Jekyll, Thoughts and Takeaways"
date:   2017-03-20 13:04:24 -0500
categories: development
tags: middleman ruby web development
header_image: "middleman-jekyll.jpg"
---
There has been some discussions as of late among my coworkers and friends about replacing WordPress.
We use it for marketing sites and so do a lot of dev shops and agencies, but it definitely has it's pain points.
Middleman and Jekyll both came up as options.
So after looking at the two I decided to write a post about the differences and similarities of each.

In regards to WordPress I found that both Middleman and Jekyll can be setup to do what WordPress does minus the CMS aspect.
Since we rely on WordPress to allow product owners and non technical founders to update their content it would
require a CMS like Contentful tied to a build system online to accomplish a similar thing. You still wouldn't get
the ability to preview your posts and other things would be missing as well, so for now we are still using WordPress.

(I am going to do an article in the future looking at WordPress alternatives and both Middleman and Jekyll will be included
in this but only alongside some cms/build/deployment strategy.)

### Differences & Similarities
Both Middleman and Jekyll are static site generators, they take some template and create static html websites from them.
Although that definition applies to both, Jekyll can better be described as a static blogging platform.
Out of the box Jekyll provides a perfect blogging platform while Middleman requires the addition of the middleman-blog gem and some setup and configuration.

#### Basic Jekyll Site Structure
{% highlight bash %}
    _config.yml
    <br>
    _data
    _drafts
    _includes
    _layouts
    _posts
    _sass
    _site
    .jekyll-metadata
    index.html
{% endhighlight %}

When setting up a new Jekyll site you are given the structure of a new blog ready to customize and start posting content.
The default Middleman site doesn't give you anything but a few directories and empty files. You have to create the blog structure or
the page structure and how the data is incorporated on your own. The middleman-blog extension gets you close to Jekyll out
of the box but still requires more configuration. Middleman ends up being the more customizable option
but for a simple blog Jekyll will have you up and running quicker.

#### Basic Middleman Site Structure
{% highlight bash %}
    .gitignore
    Gemfile
    Gemfile.lock
    config.rb
    source
        images
        index.html.erb
        javascripts
        layouts
        stylesheets
{% endhighlight %}

They both use a layout system similar to Ruby on Rails, Middleman is setup by default to use ERB templates and Jekyll is setup to use the
Liquid templating system. They both have a cli for building your site and both have development servers. Both can be configured to do things like
live reload and minification but I did find these things easier to configure in Middleman and the setup of Middleman made a bit more sense to me coming from Rails.
Especially because Middleman uses the same asset pipeline setup and helpers as Ruby on Rails.

### Which to Choose
After configuring your site they both operate in a very similar fashion. You add a new markdown file or update a data source and build your site.
That file is compiled into a new html post and the relevant links are created, tags are updated, etc. After that you upload your site to your web server and it
serves up the static html files. But I do think there are reasons to use one over the other.

If you're looking for a simple blog with little customization and a quick setup then Jekyll is probably the better option.
If you want to customize a site and have a blog in one section or more than one blog or just generate static sites from custom
data sources then Middleman is probably what you're looking for. GitHub pages use Jekyll by default but both can be hosted there.
I think I would lean toward Middleman for anything other than a typical blog. I would lean toward using Middleman for any static site,
the main reason being that updates to content would be so much easier in the future.

Both are well documented and the community seems very active around each one. They both have a plugin system but Middleman's extensions seem more robust.
I am going to be looking into solutions to replace WordPress in a future article and will include a more in depth look into both platforms tied to a CMS.
But for now I can see Middleman replacing our current use of WordPress over Jekyll and I do think Middleman would be a quicker transition for a Rails shop.
