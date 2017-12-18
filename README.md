# About

Vide is a simple Vim wrapper, which I created to manage Cscope databases. It
sources a project file called `.viderc` inside a project directory, and defines
some functions to simplify cscope database creation.

Personally, I use it together with vim `cscope_macros.vim` plugin.

# Installation.

Just copy the `bin/vide` somewhere in `$PATH`. You may also like to copy
`etc/viderc` either in `/etc/viderc` or `~/.viderc`.

# Configuration

Please, have a look inside the `viderc` file provided, all configuration
options are explained there.

# Running

As simple as that:

```
$ vide myproject
```

Vide will try to look inside predefined paths, in which it will search for
directory named `myproject`, in which a file called `.viderc` must exist.
It will then source the project file and execute vim.

So, for example, with `project_path=$HOME/projects`, it will look for the file
`~/projects/myproject/.viderc`, and if that exists, it will execute it.

Please see the example project file to have an idea what this can be useful for.

Also, note that both the configuration file and the project file are called
`viderc`. Sorry for that confusion.

# Why the hell

I created vide, because I work on kernel projects. If you must isolate your
cscope database from standard include directories and tag also assembler files,
using cscope in vim is not so comfortable.

Also, I like to be able to `make clean` and not lose the cscope database. Vide
creates the database in `~/.cache/vide/` by default, in which it is not cleaned.
