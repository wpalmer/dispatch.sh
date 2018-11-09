# Dispatch

A wrapper script for helping scripts to call other scripts, and allowing those
scripts to call scripts which call scripts that help to call other scripts.

In theory, a person calling a script should be able to override another script
that is called by adding that script to their PATH, though in practice the
priority order of such things can be tricky.

This should be nicer at some point.

extremely basic usage:

    export DISPATCH_PREFIX=task_
    ./dispatch bar

results in the execution of `task_bar.sh`

TODO:

 - specify a prefix to be used for environment variables so that unrelated `dispatch` tasks do not conflict with each-other
 - a stack of command prefixes so that `task_bar.sh` can call `task_bar_foo.sh` by saying `dispatch foo` or `task_baz.sh` by saying `dispatch /baz`
 - a configuration interface other than environment variables
 - more-intelligent handling of being included by another script
 - an interface which can be exposed to programming languages so you don't need to use bash to know about `dispatch`
 - other
