---
title: Git Gems and Local Gems
layout: post
---

<div class="message">
Git Gems, Local Gems, and Bundler
</div>

## Using git gems

Bundler is't limited to gemservers. It can load gems from remote git respositories,
so your project can use the very latest version of a gem (or a gem that your team has under
source control on a server). Unfortunately, Rubygems currently lacks the ability to handle
gems from git repositories, so any gem Bundler fetches from a git respository will not be 
visible to **gem list**.

Here's how you specify a gem to be retrieved from a git respository. A gemspec must exist
at the root of the respository.

{% highlight ruby %}
gem 'mygem', :git => 'https://github.com/jfnixon/mygem.git'
{% endhighlight %}

Without a gemspec, you must specify a version for Bundler to use.

{% highlight ruby %}
gem 'mygem', '1.1', :git => 'https://github.com/jfnixon/mygem.git'
{% endhighlight %}

If there are multiple gemspec files in the respository, you can ask for a set
of them with one request.

{% highlight ruby %}
git 'https://github.com/jfnixon/mygem.git' do
  gem 'mygem'
  gem 'anothergem'
  gem 'YAGgem'
end
{% endhighlight %}

Of course, you can specify a specific branch, ref, or tag with the **:branch**, **:ref**,
or **:tag** option. Bundler can use HTTPS, SSH, or git references.
Don't forget that **git://** is insecure and subject to a man-in-the-middle attack.
If the respository is
on github, you can use a shorthand of **:github**.

{% highlight ruby %}
gem 'mygem', :git => 'https://github.com/jfnixon/mygem.git', :branch => 'master'
gem 'mygem', :git => 'git@github.com:jfnixon/mygem.git', :ref => '8d3a7'
gem 'mygem', :git => 'git://github.com/jfnixon/mygem.git', :tag=> 'v1.1'
gem 'mygem', :github => 'jfnixon/mygem'
{% endhighlight %}

## Using local gems

Developing a gem and a project using that gem on the same machine? The Quick & Dirty hack is
to point to the local copy of the gem in your project Gemfile.

{% highlight ruby %}
gem "mygem", :path => "~/path/to/gem"
{% endhighlight %}

This points Bundler to the source code of your gem. You'll load and run *mygem* from source whenever needed
in your project. Easy, quick, and dirty.

A better way is found in 
[Bundler's docs.](http://bundler.io/v1.2/git.html#local) Bundler lets you work with
your source code control and doesn't require source to be checked out (as the first technique does).
If the git respository is local to your machine, you can set up a local override.

{% highlight shell-session %}
% bundle config local.mygem /path/to/mygem/git-respository
{% endhighlight %}

In the Gemfile, have the gem request point to a branch.

{% highlight ruby %}
gem 'mygem', :github => 'jfnixon/mygem', :branch => 'master'
{% endhighlight %}

The local override will force Bundler to use the local respository. If the repository
changes, Bundler will load the new code. A commit to the local repository will show
up in Gemfile.lock, so be careful pushing the project. If the local gem branch hasn't
been pushed out as well, pulls of the project to other machines will have a Gemfile.lock
which specifies a version of the gem which is only available locally. Bundler also ensures
that the Gemfile.lock version is present in the local repository when a local override
exists. It will tell you if a fetch of new commits is needed.

Developing a gem and a project using that gem on the same machine? The Quick & Dirty hack is
to point to the local copy of the gem in your project Gemfile.

{% highlight ruby %}
gem "mygem", :path => "~/path/to/gem"
{% endhighlight %}

This points Bundler to the source code of your gem. You'll load and run *mygem* from source whenever needed
in your project. Easy, quick, and dirty. A better way is found in 
[Bundler's docs.](http://bundler.io/v1.2/git.html#local) Bundler lets you work with
your source code control and doesn't require source to be checked out (as the first technique does).

