# Git Show Command Guide

The basic syntax of `git show` is:

```
git show [options] <object>...
```

## Common Uses

1. `git show`: Show the most recent commit on the current branch
2. `git show <commit>`: Show a specific commit
3. `git show <tag>`: Show a specific tag
4. `git show <branch>`: Show the last commit on a specific branch
5. `git show <commit>:<file>`: Show a specific file from a specific commit

## Options

### General Options

- `--pretty[=<format>]`: Pretty-print the contents of the commit logs
- `--abbrev-commit`: Show abbreviated commit IDs
- `--no-abbrev-commit`: Show full commit IDs
- `--oneline`: Shorthand for `--pretty=oneline --abbrev-commit`
- `--encoding=<encoding>`: Re-code the commit log message in the specified encoding
- `--notes[=<ref>]`: Show the notes that annotate the commit

### Diff Options

- `-u`, `-p`, `--patch`: Generate patch (default)
- `--no-patch`: Suppress diff output
- `--diff-algorithm={patience|minimal|histogram|myers}`: Choose a diff algorithm
- `--stat[=<width>[,<name-width>[,<count>]]]`: Generate a diffstat
- `--numstat`: Similar to `--stat`, but in a more machine-friendly format
- `--shortstat`: Display only the changed/insertions/deletions line from --stat
- `--dirstat[=<param1,param2,...>]`: Output the distribution of relative amount of changes for each sub-directory

### Output Formatting

- `--format=<format>`: Pretty-print the contents of the commit logs in a given format
- `--abbrev=<n>`: Show abbreviated commit IDs of length n
- `--no-abbrev`: Show full commit IDs
- `--relative-date`: Show dates relative to the current time
- `--date=<format>`: Show dates in a specific format
- `--color[=<when>]`: Show colored diff (always, never, or auto)

### Filtering Options

- `--show-signature`: Check the validity of a signed commit object

### Comparison Options

- `-w`, `--ignore-all-space`: Ignore whitespace when comparing lines
- `--ignore-space-at-eol`: Ignore changes in whitespace at EOL
- `-b`, `--ignore-space-change`: Ignore changes in amount of whitespace
- `--ignore-blank-lines`: Ignore changes whose lines are all blank

### Miscellaneous Options

- `--no-notes`: Do not show notes
- `--show-notes[=<ref>]`: Show the notes that annotate the commit
- `--standard-notes`: Show the standard notes ref (refs/notes/commits)
- `--no-standard-notes`: Do not show the standard notes ref

## Examples

1. Show the most recent commit:
   ```
   git show
   ```

2. Show a specific commit:
   ```
   git show abc123
   ```

3. Show a specific tag:
   ```
   git show v1.0.0
   ```

4. Show the last commit on a branch:
   ```
   git show feature-branch
   ```

5. Show a file from a specific commit:
   ```
   git show abc123:path/to/file.txt
   ```

6. Show commit with stat:
   ```
   git show --stat
   ```

7. Show commit in oneline format:
   ```
   git show --oneline
   ```

Remember, these options can be combined for more specific outputs. Always refer to the official Git documentation for the most up-to-date and comprehensive information.
