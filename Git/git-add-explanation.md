# Git Add Command

The `git add` command stages changes in your working directory for the next commit. 

## Basic Usage

```
git add <file>
```

This stages changes in the specified file.

## Common Options

1. `git add .`
   - Stages all new and modified files in the current directory and its subdirectories.

2. `git add -A` or `git add --all`
   - Stages all changes (new, modified, and deleted files) in the entire working tree.

3. `git add -u` or `git add --update`
   - Stages modifications and deletions, but not new files.

4. `git add -p` or `git add --patch`
   - Interactively choose hunks of patch between the index and the work tree and add them to the index.

5. `git add -i` or `git add --interactive`
   - Enters an interactive mode for more granular control over which changes to stage.

6. `git add -f` or `git add --force`
   - Allows adding otherwise ignored files.

7. `git add -n` or `git add --dry-run`
   - Don't actually add the file(s), just show if they exist and/or will be ignored.

8. `git add -v` or `git add --verbose`
   - Be verbose, showing files as they are added.

9. `git add -e` or `git add --edit`
   - Open the diff vs. the index in an editor and let the user edit it.

10. `git add --ignore-removal`
    - Ignores removed files, only staging new or modified files.

11. `git add --refresh`
    - Don't add the file(s), but only refresh their stat() information in the index.

12. `git add --ignore-errors`
    - Continue adding files even if there are errors.

## Examples

1. Stage a specific file:
   ```
   git add filename.txt
   ```

2. Stage all Python files in the current directory:
   ```
   git add *.py
   ```

3. Stage all changes interactively:
   ```
   git add -p
   ```

4. Stage all changes, including deletions, but not untracked files:
   ```
   git add -u
   ```

Remember, `git add` doesn't change the repository; it prepares changes for the next commit. Use `git status` to see which changes are staged and which are not.
