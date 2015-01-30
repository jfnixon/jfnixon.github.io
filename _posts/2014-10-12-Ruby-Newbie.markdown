---
layout: post
title: Ruby Newbie
---

<div class="message">
You are a Ruby Newbie, how do you get started with Ruby and Rails?
</div>

## Recommended startup tutorial

I've gotten several requests for OS X setup help by Ruby Newbies. One of the better setup tutorials is Daniel Kehoe's
[Install Ruby on Rails for OS X Mavericks](http://railsapps.github.io/installrubyonrails-mac.html). I'm sure he'll have 
a tutorial out for Yosemite shortly after release, but the fundamentals are the same.

First, everyone needs a package manager, and the one I like is [Homebrew](http://brew.sh/). The name is whimsical, but
it works quite well, and there are lots of packages to choose from. Homebrew is nice and will install programs in the 
*/usr/local/bin* directory--make sure your *$PATH* has */usr/local/bin* early in the list.

You'll need **Xcode**, which is Apple's development environment, and you'll need it for the command line tools which
include the compilers and other programs used by Homebrew to compile and install downloaded programs.

The *distributed source code control* program **Git** is highly recommended. Install it with Homebrew.

You'll need a *Ruby Version Manager* to handle upgrading OS X's ancient version of Ruby. I **highly** 
recommend that you leave OS X system compilers, interpreters, and gems alone. Don't install any
of these using *sudo* (with the exception of Xcode, and you really want to install Xcode from the
App Store if you are a newbie). The main choices are *RVM*, *rbenv*, and *chruby*. I'd go with [RVM](https://rvm.io/)
at first. Although it is a Ruby version manager, it also installs new rubies, and it provides *gemsets*.
Gemsets are not really needed anymore, as *Bundler* can work with all your gems in one place, but 
conceptually it is easy to see how things work with gemsets. Later, if you want, you can migrate to
*rbenv* (which I use) and decide how you want to handle gems for multiple projects (I am a fan of
the [Vendor Everything Philosophy](http://blog.johnfnixon.com/vendor-everything/)).

After you have a Ruby Version Manager, install the rubies of your choice. I'd go with a Ruby version at or
above 1.9.3 as a minimum. Earlier version of Ruby have slightly different behaviors, and you want to learn with
the current behavior (the versions above 2.0 are slightly slightly different, but the main changes are in 1.9.3).

And that should get you up and running!
