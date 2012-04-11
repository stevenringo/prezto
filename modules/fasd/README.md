Fasd
====

[Fasd][1] is a command-line productivity booster. Fasd offers quick access to
files and directories. It is inspired by tools like [autojump][2], [z][3] and
[v][4]. Fasd keeps track of files and directories previously accessed; so, that
you can quickly reference them in the command line.

You should define your own aliases to utilize the full power of fasd. For more
information please see `man fasd` or visit [fasd][1].

For completion to work, this module should be loaded **after** the *completion*
module.

Aliases
-------

Note: The Prezto Fasd configuration slightly differs from default. The `z` and
`zz` aliases have been replaced with `j` and `sj` for consistency with
[autojump][2].

### Non Interactive

  - `a`  lists files and directories.
  - `d`  lists directories.
  - `f`  lists files.
  - `z`  changes the current working directory.
  - `j`  the same as `z` for [autojump][2] converts.

### Interactive

  - `s`  selects files and directories interactively.
  - `sd` selects directories interactively.
  - `sf` selects files interactively.
  - `zz` changes the current working directory interactively.
  - `sj`  the same as `zz` for [autojump][2] converts.

### Backends

  - `v`  opens recently Vim-edited files.

### Overrides

  - `d` overrides the `dirs -v` alias defined in the *Directory* module.

Completion
----------

You can do tab completion on any fasd command (d, f, z, v, etc.).

You can type a comma-separated query on *any command* and use the following key
combination:

  - <kbd>Ctrl-x Ctrl-a</kbd> to complete files and directories.
  - <kbd>Ctrl-x Ctrl-d</kbd> to complete directories.
  - <kbd>Ctrl-x Ctrl-f</kbd> to complete files.

Alternatively, you can type extra `f,`, `d,` `,` in front of your
comma-separated query, or type extra `,,f`, `,,d`, `,,` at the end of your
comma-separated query. Such formated command-line arguments will be tab
completed via Fasd.

Authors
-------

*The authors of this module should be contacted via the [issue tracker][5].*

  - [Wei Dai](https://github.com/clvv)
  - [Sorin Ionescu](https://github.com/sorin-ionescu)

[1]: https://github.com/clvv/fasd
[2]: https://github.com/joelthelion/autojump
[3]: https://github.com/rupa/z
[4]: https://github.com/rupa/v
[5]: https://github.com/sorin-ionescu/prezto/issues

