!SLIDE commandline incremental

# Bundle Install #

<pre><code>bundle install
Using rake (0.8.7) 
Using abstract (1.0.0) 
Using activesupport (3.0.1) 
...
Your bundle is complete! It was installed into /Users/foo/.rvm/gems/ree-1.8.7-2010.02@bar
</code></pre>

!SLIDE bullets incremental

# Bundle Install vs. Update #

* 'bundle install' is conservative (won't update gems not explicitly updated in Gemfile.lock).
* 'bundle update' resolves all dependencies from scratch (ignores Gemfile.lock)

!SLIDE bullets incremental

# Bundle Install --deployment flag #

* Installs to vendor/bundle
* Will not reuse system gems
* Requires existing Gemfile.lock