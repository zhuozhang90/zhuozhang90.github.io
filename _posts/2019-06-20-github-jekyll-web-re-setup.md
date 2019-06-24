---
layout: post
title: "Re-Set Up Jekyll to Host Static Website on GitHub"
date: 2019-06-20
categories: [web, jekyll]
---

I've been wanting to set up a personal website for a while and I ended up choosing GitHub instead of WordPress for hosting my static website. One of the main reasons I decided to use GitHub is because it supports uploading blog posts in MarkDown and it just makes it easier and more portable in case I want to keep a copy of everything I post.

GitHub uses Jekyll to compile the pages from md to html and I have had to set up Jekyll more than a few times since I upgraded my system every few months. There're some tricky parts of setting up Ruby and Jekyll after the initial project set up so I'm going to walk through setting up the environment for non-first time use.

Normally what happens to me is that when I reinstall or upgrade my system, I'll have to reconfigure my environment for ruby and jekyll. To say this not without a hint of shame, I reinstall my system way too much. Not even just distro-hopping. When things get too messed up sometimes it's just easier to start from a clean slate. I generally try to use virtual machines and virtual environments (e.g. `pipenv` for python) it's still inevitable sometimes. 

So without further ado, this is how I re-setup my environment on currently Manjaro Linux for jekyll-backed static website.

Make sure that this is not the first time setting up the environment for the website as we need the `Gemfile` to exist in the directory. If not follow the official tutorial. 

### Install Ruby and bundler

```bash
Sudo Pacman -Syu ruby
gem install bundler
```
Then ruby's gonna tell you your gem executables directory is not in your `$PATH`, with something like `WARNING:  You don't have ~/.gem/ruby/2.6.0/bin in your PATH, gem executables will not run.` so now we just need to add it.

### Add Gem Executables to PATH

Best way I found is to simply add it to your `~/.profile` file if you are using bash. 

```bash
vim ~/.profile
```
then add the line `export PATH="$PATH:~/.gem/ruby/2.6/bin"`, you might have to change the version number based on which version of ruby you just installed. 

Then exit out of vim, and we are ready to install the packages.

### Install Packages With Gem

Before `gem install` we need to configure the `Gemfile` first. Simply add `gem 'github-pages', group: :jekyll_plugins` right below `source 'https://rubygems.org'` (add this one first if not present in the Gemfile already).

Then simply `bundle install`. If it's been a while since last time you actually worked on the project and updated the dependencies then it'll probably fail and bundler's gonna say it couldn't find compatible versions or jekyll or something, as the versions listed in our Gemfile.lock is way too old, so we'll need to `bundle update`, which installs the required packages but newer versions. After inputting the password for sudo, the packages will be all set. 

Now simply edit the files then `jekyll build` to build the website and `jekyll serve` to serve on local machine. 





