---
layout: post
title: Ruby Gems
---

<div class="message">
To fully understand the Rails workflow, we need to understand the various tools.
Let's start with Ruby Gems.
</div>

## What are Ruby Gems?

Gems are simply a documented way of sharing Ruby code. Let's look at a gem!

{% highlight shell-session %}
2.1.2 hubble ~/test % gem list yamlconfig -r

*** REMOTE GEMS ***

layeredyamlconfig (1.4.4)
yamlconfig (0.2.2)
2.1.2 hubble ~/test %
{% endhighlight %}

Download it and unpack it, and we'll see the rake executable, test code, source code, and 
metadata defining the authors, target platform, dependencies on other gems, and so forth. Gems are just
packages for sharing Ruby code and executables.

{% highlight shell-session %}
2.1.2 hubble ~/test % gem fetch yamlconfig
Fetching: yamlconfig-0.2.2.gem (100%)
Downloaded yamlconfig-0.2.2
2.1.2 hubble ~/test % ls
yamlconfig-0.2.2.gem
2.1.2 hubble ~/test % gem unpack yamlconfig-0.2.2.gem
Unpacked gem: '/Users/jfnixon/test/yamlconfig-0.2.2'
2.1.2 hubble ~/test % tree
.
├── yamlconfig-0.2.2
│   ├── Gemfile
│   ├── Rakefile
│   ├── lib
│   │   ├── LICENSE
│   │   ├── yamlconfig
│   │   │   └── version.rb
│   │   └── yamlconfig.rb
│   └── spec
│       ├── data
│       │   ├── accessor_config
│       │   ├── accessor_config_tmp
│       │   ├── complex_values
│       │   ├── config
│       │   ├── empty_file
│       │   ├── flatulentmonkey
│       │   └── freakboy
│       ├── spec_helper.rb
│       └── yamlconfig_spec.rb
└── yamlconfig-0.2.2.gem

5 directories, 15 files
2.1.2 hubble ~/test %
{% endhighlight %}
