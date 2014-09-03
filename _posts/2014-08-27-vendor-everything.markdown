---
layout: post
title: Vendor everything
---

<div class="message">
For Ruby projects, manage dependencies without RVM gemsets.
</div>

## Vendor everything to document your code and manage dependencies

This insight comes from 
[Ryan McGeary's post](http://ryan.mcgeary.org/2011/02/09/vendor-everything-still-applies/)

* Check your .ruby-version file into version control; it’s a form of documentation.
* Avoid RVM gemsets for your applications; Bundler solves the same problem in a better way (bundle install --path vendor).
* Keep a cache of your gem dependencies in version control using bundle package.
* This only applies to Ruby applications; gem development is a different beast.

```
$ bundle install --path vendor
$ bundle package
$ echo 'vendor/ruby' >> .gitignore
```
