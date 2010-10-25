!SLIDE bullets incremental

# Cap & Bundler Working Together #

* This is the hard part of the presentation....
* Wait for it...
* Wait for it...

!SLIDE bullets

# Add to your Capfile #

<pre style="margin-left: 200px">require 'bundler/capistrano'</pre>

* This basically does a 'bundle install' after 'deploy:update_code'
* [Here is exactly what is does](http://github.com/carlhuda/bundler/blob/master/lib/bundler/deployment.rb)
* You can always hand code it for more control.