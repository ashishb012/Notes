# Git Diff Command

The basic syntax of `git diff` is:

```
git diff [options] [<commit>] [--] [<path>...]
```

## Common Uses

1. `git diff`: Show unstaged changes in the working directory
2. `git diff --staged` or `git diff --cached`: Show staged changes
3. `git diff <commit>`: Show changes between working directory and a specific commit
4. `git diff <commit1> <commit2>`: Show changes between two commits
5. `git diff <branch1> <branch2>`: Show changes between two branches

## Options

### Diff Options

- `--stat`: Show a summary of changes (insertions, deletions) for each file
- `--numstat`: Similar to `--stat`, but in a more machine-friendly format
- `--shortstat`: Display only the changed/insertions/deletions line from --stat
- `--summary`: Display a condensed summary of extended header information
- `--patch-with-stat` or `-p --stat`: Show both textual and statistical diff
- `--name-only`: Show only names of changed files
- `--name-status`: Show names and status of changed files

### Output Formatting

- `--color[=<when>]`: Show colored diff (always, never, or auto)
- `--word-diff[=<mode>]`: Show word diff, highlighting intra-line changes
- `--unified=<n>`: Generate diffs with <n> lines of context
- `--output=<file>`: Output to a specific file instead of stdout

### Filtering Options

- `--diff-filter=[(A|C|D|M|R|T|U|X|B)...]`: Select only files with specified status
- `-G<regex>`: Look for differences whose added or removed line matches the given regex
- `-S<string>`: Look for differences that change the number of occurrences of the specified string

### Comparison Options

- `-w` or `--ignore-all-space`: Ignore whitespace when comparing lines
- `--ignore-space-at-eol`: Ignore changes in whitespace at EOL
- `-b` or `--ignore-space-change`: Ignore changes in amount of whitespace
- `--ignore-blank-lines`: Ignore changes whose lines are all blank
- `--function-context`: Show whole surrounding functions of changes

### Pathspec Options

- `--`: Used to separate paths from revisions

### Misc Options

- `--no-index`: Compare two paths on the filesystem (not necessarily in a git repo)
- `--exit-code`: Exit with 1 if there were differences, 0 otherwise
- `--quiet`: Disable all output of the program

## Examples

1. Show unstaged changes:

   ```
   git diff
   ```

2. Show staged changes:

   ```
   git diff --staged
   ```

3. Compare with a specific commit:

   ```
   git diff abc123
   ```

4. Compare two branches:

   ```
   git diff main feature-branch
   ```

5. Show stat summary:

   ```
   git diff --stat
   ```

6. Show word-level differences:
   ```
   git diff --word-diff
   ```

Remember, these options can be combined for more specific outputs. Always refer to the official Git documentation for the most up-to-date and comprehensive information.
