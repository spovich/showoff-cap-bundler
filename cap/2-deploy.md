!SLIDE bullets incremental

# Capistrano Deploy #

* Strategy
* Dependencies (Bundler)
* Deploy Tasks
* Task Hooks
* Sample Deploy

!SLIDE bullets commandline

# Deploy Strategy #

* Maintain git repo on the server
* Define how and where to put code

<pre style="margin-left: 200px">
set :use_sudo, false
set :deploy_to, "#{web_root}/#{user}/#{application}"
set :deploy_via, :remote_cache
</pre>

!SLIDE bullets

# Deploy Dependencies #

* We will address that later in the bundler section

!SLIDE bullets

# Deploy Tasks #

* 'cap deploy' runs several standard tasks
* Won't run first time without setup

<pre style="margin-left: 200px">
# cap deploy:setup
# cap deploy:check
</pre>

!SLIDE bullets commandline

# Task Hooks #

* Extend the standard deploy task by defining additional tasks via hooks

<pre style="margin-left: 100px">
before 'deploy', 'deploy:check'
before 'deploy', 'deploy:web:disable'

after 'deploy:update_code', 'bundler:bundle_install'
after 'deploy:update_code', 'app_setup' if run_app_setup
after 'deploy:update_code', 'db_migrate'

after 'deploy:symlink', 'clear_cache'

after 'deploy', 'deploy:web:enable'
</pre>

!SLIDE bullets

# Sample Deploy #

* [jump to shell]