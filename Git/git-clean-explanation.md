# Git Clean Command

The `git clean` command is used to remove untracked files from the working directory. This command can be quite dangerous as it permanently deletes files that are not tracked by Git, so it should be used with caution.

## Basic Usage

```
git clean [<options>] [--] <path>...
```

Without any options, `git clean` will do nothing. You need to add force options to actually delete files.

## Common Options

1. `git clean -n` or `git clean --dry-run`
   - Don't actually remove anything, just show what would be done.

2. `git clean -f` or `git clean --force`
   - Force git to delete the untracked files. This is required to actually delete files.

3. `git clean -d`
   - Remove untracked directories in addition to untracked files.

4. `git clean -i` or `git clean --interactive`
   - Show what would be deleted and give a prompt to choose which files to delete.

5. `git clean -x`
   - Remove ignored files as well as untracked files.

6. `git clean -X`
   - Remove only ignored files.

## Advanced Options

7. `git clean -q` or `git clean --quiet`
   - Be quiet, only report errors, but not the files that are successfully removed.

8. `git clean -e <pattern>` or `git clean --exclude=<pattern>`
   - Use the given pattern in addition to the standard ignore rules.

9. `git clean -x -i`
   - Interactively clean ignored files as well.

10. `git clean -df`
    - Remove untracked files and directories forcefully.

11. `git clean -f -d -x`
    - Remove untracked and ignored files and directories.

## Examples

1. See what files would be deleted:
   ```
   git clean -n
   ```

2. Forcefully remove untracked files:
   ```
   git clean -f
   ```

3. Remove untracked files and directories:
   ```
   git clean -fd
   ```

4. Interactively choose which untracked files to delete:
   ```
   git clean -i
   ```

5. Remove both untracked and ignored files:
   ```
   git clean -fx
   ```

6. Remove only ignored files:
   ```
   git clean -fX
   ```

7. Remove untracked files, excluding those with .txt extension:
   ```
   git clean -f -e "*.txt"
   ```

## Notes and Best Practices

- Always run `git clean` with the `-n` option first to see what will be deleted.
- `git clean` only operates on untracked files by default. To remove ignored files as well, use the `-x` option.
- The `-i` (interactive) option is safer as it allows you to review and confirm each deletion.
- `git clean` can be dangerous as it permanently deletes files. Make sure you have backups or are certain you want to delete the files.
- `git clean` does not remove files listed in `.gitignore` by default. Use `-x` to remove these as well.
- If you want to remove all build artifacts and untracked files to get a clean working directory, a common command is `git clean -fdx`.
- Remember that `git clean` only removes untracked files. It doesn't affect tracked files or the staging area.
- If you're unsure, you can always stash your changes with `git stash -u` (which includes untracked files) instead of cleaning.

Remember, `git clean` is a powerful command that permanently deletes files. Always double-check what you're deleting, especially when using the force options. It's often safer to manually delete files or use interactive mode if you're unsure.
