oh-my-zsh-custom
================

My self-written contents of the oh-my-zsh custom directory, replaces the annoying forking.
One can use these things by copying them to the ~/.oh-my-zsh/custom directory or replacing the directy with a clone of this repository.

contents
========

plugins/autovirtualenv
----------------------

Automatically detect Python virtualenvs by searching for their bin/activate scripts upon the change of a directory.
If such a script is found, the virtualenv is automatically activated (and a message is shown to you). The environment stays activated
until you leave the main directory (so within any sub-folders the environment stays activated).

If you leave the base folder the environment gets disabled and a message is shown to you.

Example:
```╭irrenhaus > ~
╰> cd envtest 
Found virtualenv. Activating...
╭irrenhaus > ~/envtest [test]
╰> cd ..
Deactivating virtualenv: /home/irrenhaus/envtest/test
╭irrenhaus > ~
╰> ```

Notice how the environment's name is displayed within the prompt. You can do that by using the supplied current_virtual_env() method which
returns a string like "[name]".

plugins/virtualpath
-------------------

This plugin looks for a file named ".virtualpath.conf" within the current directory upon each directory change.
If the file is found each line within the file is appended to the PATH variable until you leave the directory (that is including
subdirectories, so as soon as you change to _any_ different folder the PATH variable is reset).
This enables you to have per-directory custom PATH entries.

Example:
```╭irrenhaus > ~
╰> cd pathtest 
Adding virtualpath /home/irrenhaus/bin to the PATH variable.
╭irrenhaus > ~/pathtest
╰> cat .virtualpath.conf 
/home/irrenhaus/bin
╭irrenhaus > ~/pathtest
╰> cd ..
Resetting PATH variable```

themes/irrenhaus-dual
---------------------

Well, my currently perferred custom theme, try it and use it if you like it.
Be aware, this theme uses two lines per command (you can see it in the examples above).
The theme includes a display for git repositories.
