---
title: Local Gems
layout: post
---

<div class="message">
Local Gems and Bundler
</div>

## Using local gems

Developing a gem and a project using that gem on the same machine? The Quick & Dirty hack is
to point to the local copy of the gem in your project Gemfile.

{% highlight ruby %}
gem "mygem", :path => "~/path/to/gem"
{% endhighlight %}

This points Bundler to the source code of your gem. You'll load and run *mygem* from source whenever needed
in your project. Easy, quick, and dirty. A better way is found in 
[Bundler's docs.](http://bundler.io/v1.2/git.html#local) Bundler lets you work with
your source code control and doesn't require source to be checked out (as the first technique does).

Set up a local override like this:




