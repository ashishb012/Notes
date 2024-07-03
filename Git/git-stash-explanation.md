# Git Stash Command

The basic syntax of `git stash` is:

```
git stash <subcommand> [<options>]
```

## Common Subcommands

1. `git stash push`: Save your local modifications to a new stash (default action if no subcommand is given)
2. `git stash list`: List all stashes
3. `git stash show`: Show the changes recorded in the stash
4. `git stash apply`: Apply a stash and keep it in the stash list
5. `git stash pop`: Apply a stash and remove it from the stash list
6. `git stash drop`: Remove a stash from the list
7. `git stash clear`: Remove all stashes
8. `git stash branch`: Create a new branch from a stash

## Subcommands and Their Options

### git stash push [<options>]

Options:

- `-m <message>`, `--message <message>`: Specify a stash message
- `-p`, `--patch`: Interactively select hunks to stash
- `-k`, `--keep-index`: Keep the index; stash only unstaged changes
- `-u`, `--include-untracked`: Stash untracked files too
- `-a`, `--all`: Stash untracked and ignored files too
- `-q`, `--quiet`: Suppress feedback messages

Example:

```
git stash push -m "Work in progress for feature X"
```

### git stash list [<options>]

Options:

- `--pretty[=<format>]`: Pretty-print the contents of the stash logs
- `--format=<format>`: Specify format for the output
- `--date=<format>`: Specify date format

Example:

```
git stash list --pretty=format:"%gd: %s"
```

### git stash show [<options>] [<stash>]

Options:

- `-p`, `--patch`: Show the stash entry in patch form
- `--stat`: Show a diffstat of the stash entry
- `--color[=<when>]`: Use color in output
- `-u`, `--include-untracked`: Show untracked files

Example:

```
git stash show -p stash@{1}
```

### git stash apply [<options>] [<stash>]

Options:

- `--index`: Try to reinstate index changes
- `-q`, `--quiet`: Suppress feedback messages

Example:

```
git stash apply stash@{2}
```

### git stash pop [<options>] [<stash>]

Options:

- `--index`: Try to reinstate index changes
- `-q`, `--quiet`: Suppress feedback messages

Example:

```
git stash pop
```

### git stash drop [<options>] [<stash>]

Options:

- `-q`, `--quiet`: Suppress feedback messages

Example:

```
git stash drop stash@{1}
```

### git stash clear

This command takes no options.

Example:

```
git stash clear
```

### git stash branch <branchname> [<stash>]

This command creates a new branch with the stash applied, then drops the stash if it applied successfully.

Example:

```
git stash branch new-feature stash@{1}
```

## Additional Options

- `--keep-index`, `-k`: Used with `push` and `save` (deprecated) commands. All changes already added to the index are left intact.
- `--no-keep-index`: Used with `push` and `save` (deprecated) commands. Stash all the changes in the index and working tree.
- `--patch`, `-p`: Used with `push` and `save` (deprecated) commands. Interactively select hunks from the diff between HEAD and the working tree to be stashed.

Remember, stashes are stored on a stack, so you can have multiple stashes. The most recent stash is `stash@{0}`, the one before it is `stash@{1}`, and so on. If you don't specify a stash, Git assumes you mean the most recent one.

Always refer to the official Git documentation for the most up-to-date and comprehensive information.
