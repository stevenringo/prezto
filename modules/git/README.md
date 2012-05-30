Git
===

Enhances the [Git][1] distributed version control system. Provides Git aliases
and functions.

Git **1.7.2** is the [minimum][7] required version.

Settings
--------

### Git Information

This module allows for the creation of custom prompts for Git repositories.
To do so, each available information can be formatted separately then merged
into `$PROMPT` and `$RPROMPT`.

#### Available Information

Each information has to be formatted before being inserted into the prompt.

The format is defined with a `zstyle` by providing the name of the element we
want to format, and the format.

    zstyle ':omz:module:git' Name 'Format code'
    zstyle ':omz:module:git' branch 'Branch: %b'

Here is an exhaustive list of the elements and the format code that can be used:

Name      | Format Code | Content
--------- | ----------- | ----------------------------------------
action    | %s          | Special action name (am, merge, rebase).
added     | %a          | Indicator to notify of added files.
ahead     | %A          | Indicator to notify of ahead branch.
branch    | %b          | Branch name.
behind    | %B          | Indicator to notify of behind branch.
commit    | %c          | SHA-1 hash.
deleted   | %d          | Indicator to notify of deleted files.
dirty     | %D          | Indicator to notify of dirty files.
modified  | %m          | Indicator to notify of modified files.
position  | %p          | Current position in the git tree.
renamed   | %r          | Indicator to notify of renamed files.
remote    | %R          | Remote name.
stashed   | %S          | Indicator to notify of stashed files.
untracked | %u          | Indicator to notify of untracked files.
unmerged  | %U          | Indicator to notify of unmerged files.

#### PROMPT and RPROMPT

Once every element has been pre-formated,

  - prompt, Left prompt.
  - rprompt, Right prompt.

#### Conditional formatting

It's possible to add some conditions.

#### Ignore submodule.

Getting the current Git status from a project with submodules can take a long
time.

##### Enable the ignore mode

It's possible to ignore the submodule when it is 'dirty', 'untracked', 'all', or
'none':

    zstyle ':omz:module:git:ignore' submodule ''

Hub
---

Adds GitHub knowledge to the Git command.

https://github.com/defunkt/hub

Automatically creates the `git` alias if [`hub`][2] is installed.

Aliases
-------

### Git

  - `g` is a stupid content tracker.

### Branch

  - `gb` lists, creates, renames, and deletes branches.
  - `gbc` creates a new branch.
  - `gbl` lists branches and their commits.
  - `gbL` lists local and remote branches and their commits.
  - `gbs` lists branches and their commits with ancestory graphs.
  - `gbS` lists local and remote branches and their commits with ancestory
    graphs.
  - `gbx` deletes a branch.
  - `gbX` deletes a fully merged branch.
  - `gbm` renames a branch.
  - `gbM` renames a branch even if the new branch name already exists.


### Commit

  - `gc` records changes to repository.
  - `gca` stages all modified and deleted files.
  - `gcm` records changes to repository with the given message.
  - `gco` checkouts a branch or paths to working tree.
  - `gcO` checkouts paths to working tree using the *HEAD* commit.
  - `gcf` amends the tip of the current branch using the same log message as
    *HEAD*.
  - `gcp` applies changes introduced by existing commits, fast forwards, if
    possible).
  - `gcP` applies changes introduced by existing commits without commiting.
  - `gcr` reverts existing commits by reverting the patches and recording new commits.
  - `gcR` removes the *HEAD* commit.
  - `gcs` displays various types of objects.
  - `gcl` displays lost commits.

### Data

  - `gd` displays information about files in the index and the working tree.
  - `gdc` lists cached files.
  - `gdx` lists deleted files.
  - `gdm` lists modified files.
  - `gdu` lists untracked files.
  - `gdk` lists killed files.
  - `gdi` lists ignored files.

### Fetch

  - `gf` downloads objects and references from another repository.
  - `gfc` clones a repository into a new directory.
  - `gfm` fetches from and merge with another repository or local branch.
  - `gfr` fetches from and rebase on another repository or local branch.

### Index

  - `gia` adds file contents to the index.
  - `giA` adds file contents to the index interactively.
  - `giu` adds file contents to index (update only files git already knows about).
  - `gid` displays changes between index and named commit.
  - `giD` displays changes between index and named commit (Ignore white spaces).
  - `gir` resets current HEAD to specified state.
  - `giR` resets current index to specified state.
  - `gix` removes files/directories from the index (recursively).
  - `giX` removes files/directories from the index (recursively/forced).
  - `gig` prints lines in the index matching a pattern.

### Conflict

  - `gkl` lists unmerged files.
  - `gka` adds every unmerged file.
  - `gke` starts merge-tool on every unmerged file.
  - `gko` checks out stage #2 for unmerged paths.
  - `gkO` checks out stage #2 for every unmerged paths.
  - `gkt` checks out stage #3 for unmerged paths.
  - `gkT` checks out stage #3 for every unmerged paths.

### Log

  - `gl` displays commit logs (display commits in topological order).
  - `gls` displays commits diffstats.
  - `gld` displays commits full-diff.
  - `glo` displays commit logs (one line).
  - `glg` displays commit logs (as a graph).
  - `glb` displays commit logs (brief).
  - `glc` displays commit short-logs.

### Merge

  - `gm` joins two or more development histories together.
  - `gmC` performs the merge but do not commit the result.
  - `gmF` generates a merge commit even if the merge resolved as a fast-forward.
  - `gma` aborts the current conflict resolution process, and try to reconstruct
    the pre-merge state.
  - `gmt` runs merge conflict resolution tools to resolve merge conflicts.

### Push

  - `gp` updates remote refs along with associated objects.
  - `gpf` forces update remote refs along with associated objects.
  - `gpa` updates remote branches along with associated objects.
  - `gpA` updates every remote refs along with associated objects.
  - `gpt` updates remote tags along with associated objects.
  - `gpc` adds origin as an upstream reference for the current branch that is up
    to date or pushed.
  - `gpp` pulls and push from origin to origin.

### Rebase

  - `gr` fasforward-ports local commits to the updated upstream head.
  - `gra` aborts current rebase.
  - `grc` continues after resolving merge conflict.
  - `gri` makes a list of commits to be rebased and open in $EDITOR.
  - `grs` skips the current patch.

### Remote

  - `gR` manages set of tracked repositories.
  - `gRl` displays remote url after name.
  - `gRa` adds a new remote.
  - `gRx` removes a remote and all associated tracking branches.
  - `gRm` renames a remote and update all associated tracking branches.
  - `gRu` fetchs updates for a set of remotes.
  - `gRc` deletes all stale tracking branches for a remote.
  - `gRs` displays information about a given remote.
  - `gRb` calls the `git-hub` function.

### Stash

  - `gs` stashes away changes to dirty working directory.
  - `gsa` applys the changes recorded in the stash.
  - `gsc` removes all the stashed states.
  - `gsx` removes a single stashed state from the stash list.
  - `gsl` lists the stashes that you currently have.
  - `gsL` displays the diffstat of the last stash.
  - `gsp` removes and apply a single stashed state from the stash list.
  - `gsr`
  - `gss` saves your local modifications to a new stash (and untracked).
  - `gsS` saves your local modifications to a new stash (interactively).

### Submodule

  - `gS` initializes update, or inspect submodules.
  - `gSa` adds given repository as a submodule.
  - `gSf` evaluates shell command in each checked-out submodule.
  - `gSi` initializes a submodule.
  - `gSl` displays the status of a submodule.
  - `gSs` displays commit summary between given commit and working tree/index.
  - `gSu` updates a submodule.
  - `gSU` updates or init a submodule (recursively).

### Working directory

  - `gws` displays working-tree status (short format).
  - `gwS` displays working-tree status.
  - `gwd` displays changes between commits, commit and working tree, etc.
  - `gwD` displays changes between commits, commit and working tree, etc. (without
    white spaces).
  - `gwr` resets current HEAD to specified state, do not touch the index file nor
    the working tree.
  - `gwR` resets current HEAD to specified state,match the working tree and index
    to the given tree.
  - `gwc` removes untracked files from working tree (dry-run).
  - `gwC` removes untracked files and directories from working tree.
  - `gwx` removes files from the working tree and from the index.
  - `gwX` removes files from the working tree and from the index.
  - `gwg` prints lines matching a pattern.

### Shadows

The following aliases may shadow system commands:

  - `gpt` shadows the [GUID partition table maintannce utility][4].
  - `gs` shadows the [Ghostscript][5].

If you frequently use the above commands, you may wish to remove the aliases
from this module or to disable them at the bottom of the zshrc with `unalias`.

You can temporarily bypass an alias by prefixing them with a backword slash:
`\gpt`.

Functions
---------

  - `git-branch-current` displayss the current Git branch.
  - `git-commit-lost`
  - `git-dir`
  - `git-hub-short-url` shortenss GitHub URLs.
  - `git-hub` opens the [GitHub][3] repository in the default browser.
  - `git-info` gets the Git status information.
  - `git-root` displays the Git repository root.
  - `git-stash-clear-interactive`
  - `git-stash-dropped`
  - `git-stash-recover`

Authors
-------

*The authors of this module should be contacted via the [issue tracker][6].*

  - [Sorin Ionescu](https://github.com/sorin-ionescu)
  - [Colin Hebert](https://github.com/ColinHebert)

[1]: http://www.git-scm.com/
[2]: https://github.com/defunkt/hub
[3]: http://www.github.com
[4]: http://www.manpagez.com/man/8/gpt/
[5]: http://linux.die.net/man/1/gs
[6]: https://github.com/sorin-ionescu/oh-my-zsh/issues
[7]: https://github.com/sorin-ionescu/oh-my-zsh/issues/219

