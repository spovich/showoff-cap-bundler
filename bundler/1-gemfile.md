!SLIDE bullets incremental

# Anatomy of a Gemfile #

* [Gemfile Syntax](http://gembundler.com/man/gemfile.5.html)
* Evaluated as Ruby code
* Sources options
* Gems options
* Using Blocks in Gemfile
* Sample Gemfile

!SLIDE bullets incremental

# Gemfile 'source' #

* Must be valid rubygems repositories
* Roll your own, if you are adventurous
* Can have multiple sources
* Searched in order of declaration
* Individual gem can have a source

!SLIDE bullets incremental

# Gemfile 'gem' #

* Only gem name is required
* Everything else is optional
* Options: version, require, platforms (jruby), git, path

!SLIDE bullets incremental

# Gemfile Blocks #

* Group block is most commonly used
* Only install those gems in the specified environment
* Allows you to not pollute production with dev & testing gems
* Other block forms: Git, Path, Platforms

!SLIDE commandline

# Sample Gemfile #

<pre style="font-size: 1.4em;">
source 'http://rubygems.org'

gem 'rails',                  '= 3.0.1'
gem 'pg',                     '~> 0.9.0'
gem 'exception_notification', :git => 'http://github.com/rails/exception_notification.git'
gem 'will_paginate',          :path => 'vendor/rails' # custom version of gem
gem 'nokogiri',               :platforms => [:mri_18, :jruby]

group :development, :test do
  gem 'redgreen'
  gem 'silent-postgres'
  gem 'ruby-debug'
  gem 'rspec-rails', '~> 2.0.1'
end
</pre>
