!SLIDE bullets incremental

# Capistrano Basics #

* 20,000 ft Capistrano
* Install Capistrano
* [Capistrano Documentation](http://www.capify.org)
* Cap'ify your app
* Cap Recommendations

!SLIDE bullets incremental

# 20,000 ft Capistrano #

* What is it?
* How does it work?
* Why should I use it?

!SLIDE commandline incremental

# Install Capistrano #

<pre><code>gem install capistrano
Successfully installed capistrano-2.5.19
1 gem installed
Installing ri documentation for capistrano-2.5.19...
Installing RDoc documentation for capistrano-2.5.19...</pre></code>

!SLIDE bullets incremental

# Cap'ify your app #

* Need 'Capfile' in your app root
* For rails, 'Capfile' loads config/deploy.rb
* For this talk, I will use 'Capfile' and 'deploy.rb' interchangeably

!SLIDE commandline

# Cap'ifisticationalizing #

* <pre><code>$capify ./
[add] writing `./Capfile'
[add] writing `./config/deploy.rb'
[done] capified!</pre></code>