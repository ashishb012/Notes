# Git Config Command

The `git config` command is used to get and set repository or global options. These configuration variables control various aspects of Git's operation and appearance.

## Basic Syntax

```
git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] name [value [value-pattern]]
git config [<file-option>] [--type=<type>] --add name value
git config [<file-option>] [--type=<type>] --replace-all name value [value-pattern]
git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] --get name [value-pattern]
git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] --get-all name [value-pattern]
git config [<file-option>] [--type=<type>] [--show-origin] [--show-scope] [-z|--null] [--name-only] --get-regexp name_regex [value-pattern]
git config [<file-option>] [--type=<type>] [-z|--null] --get-urlmatch name URL
git config [<file-option>] --unset name [value-pattern]
git config [<file-option>] --unset-all name [value-pattern]
git config [<file-option>] --rename-section old_name new_name
git config [<file-option>] --remove-section name
git config [<file-option>] [--show-origin] [--show-scope] [-z|--null] [--name-only] -l | --list
git config [<file-option>] --get-color name [default]
git config [<file-option>] --get-colorbool name [stdout-is-tty]
git config [<file-option>] -e | --edit
```

## Common Options

### File-location Options

1. `--system`: Use system-wide configuration file.
2. `--global`: Use global configuration file.
3. `--local`: Use repository-specific configuration file.
4. `--worktree`: Use per-worktree configuration file.
5. `-f <file>, --file <file>`: Use given config file.
6. `--blob <blob>`: Read config from given blob object.

### Action Options

7. `--get`: Get the value for a given key.
8. `--get-all`: Get all values for a multi-valued key.
9. `--get-regexp`: Get values for keys matching regex.
10. `--get-urlmatch`: Get value specific for the URL.
11. `--replace-all`: Replace all matching variables.
12. `--add`: Add a new variable.
13. `--unset`: Remove a variable.
14. `--unset-all`: Remove all matching variables.
15. `--rename-section`: Rename a section.
16. `--remove-section`: Remove a section.
17. `-l, --list`: List all variables.
18. `--get-color`: Find color setting.
19. `--get-colorbool`: Find color setting (boolean).
20. `-e, --edit`: Open an editor to modify the specified config file.

### Type Options

21. `--bool`: Value is "true" or "false".
22. `--int`: Value is decimal number.
23. `--bool-or-int`: Value is --bool or --int.
24. `--path`: Value is a path (file or directory name).
25. `--expiry-date`: Value is an expiry date.

### Other Options

26. `--name-only`: Show variable names only.
27. `--show-origin`: Show origin of config (file, standard input, blob, command line).
28. `--show-scope`: Show scope of config (local, global, system, command).
29. `-z, --null`: Terminate values with NUL byte.
30. `--includes`: Respect include directives on lookup.
31. `--no-includes`: Do not respect include directives on lookup.

## Examples

1. Set your name for all repositories:
   ```
   git config --global user.name "John Doe"
   ```

2. Set your email for all repositories:
   ```
   git config --global user.email "johndoe@example.com"
   ```

3. Set the default branch name for new repositories:
   ```
   git config --global init.defaultBranch main
   ```

4. Set your preferred text editor:
   ```
   git config --global core.editor "vim"
   ```

5. List all configurations:
   ```
   git config --list
   ```

6. Get a specific configuration value:
   ```
   git config user.name
   ```

7. Edit the global configuration file:
   ```
   git config --global --edit
   ```

8. Set a repository-specific configuration:
   ```
   git config --local user.email "work@example.com"
   ```

9. Unset a configuration value:
   ```
   git config --unset user.name
   ```

10. Set an alias:
    ```
    git config --global alias.co checkout
    ```

## Common Configurations

- `user.name`: Your full name
- `user.email`: Your email address
- `core.editor`: Your preferred text editor
- `init.defaultBranch`: The default branch name for new repositories
- `color.ui`: Enables/disables color output
- `push.default`: Defines the default push behavior
- `pull.rebase`: Whether to rebase or merge when pulling
- `alias.*`: Custom shortcuts for Git commands

Remember, `git config` is a powerful tool for customizing your Git environment. It allows you to set up Git to work the way you prefer, both globally and for specific repositories.
