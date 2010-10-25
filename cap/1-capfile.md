!SLIDE bullets incremental

# Anatomy of a Capfile #

* Environment/Variables
* Roles
* Tasks
* Show Working Capfile

!SLIDE bullets incremental

# Capfile Variables #

* Set them
* Prompt for them
* Use them!
* [Capfile Variables Documentation](http://github.com/capistrano/capistrano/wiki/2.x-Significant-Configuration-Variables)

!SLIDE commandline

# Capfile Environment/Variables #

<pre style="font-size: 1.7em;">
set :application, 'foo' # system
set :user, 'bar' # system

set :rake, '/opt/ree/bin/rake' # system
set :web_root, '/var/www' # system

set :staging_server, 'tacquito.foobar.com' # arbitrary
set :production_server, 'chalupa.foobar.com' # arbitrary

set :scm, :git # system
set :repository, "git@git.foobar.com:#{application}.git" # system

branch = Capistrano::CLI.ui.ask("Deploy branch ('master' is default): ")
branch = 'master' if branch.empty?
set :branch, branch # system
</pre>

!SLIDE bullets commandline

# Capfile Roles #

* Declare which server takes which role

<pre style="margin-left: 200px">
role :app, 'www.foobar.com'
role :web, 'www.foobar.com'
role :db, 'www.foobar.com'
</pre>

* OR declare a 'server' for simpler configs

<pre style="margin-left: 200px">
server 'www.foobar.com', :app, :web, :db
</pre>

!SLIDE bullets commandline

# Capfile Tasks #

* Can do anything you can do from shell
* Can run application rake tasks
* List Capfile Tasks

<pre style="margin-left: 200px">
$ cap -T
</pre>

* Simple Capfile Task

<pre style="margin-left: 200px">
desc "List Remote Web Root"
task :list_web_root, :roles => :web do
  run "ls -la /var/www"
end
</pre>

!SLIDE bullets

# Disect a working Capfile #

* [jump to text editor]