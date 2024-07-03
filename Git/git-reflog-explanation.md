# Git Reflog Command

The `git reflog` command manages reflog information. A reflog records when the tip of branches and other references were updated in the local repository. It's particularly useful for recovering lost commits or branches.

## Basic Syntax

```
git reflog [<subcommand>] <options>
```

## Subcommands

1. `show` (default): Show log of the reference (default: HEAD)
2. `expire`: Prune older reflog entries
3. `delete`: Delete entries from the reflog
4. `exists`: Check if a ref has a reflog

## Common Options

### General Options

1. `--all`: Process the reflogs of all references
2. `--single-worktree`: Only accept a single worktree
3. `--create-reflog`: Create a reflog if it does not exist
4. `--no-create-reflog`: Do not create a reflog if it does not exist
5. `--updateref`: Update the ref with the sha1 of the top reflog entry
6. `--rewrite`: Adjust reflogs so old SHA-1s point to new ones
7. `--stale-fix`: Prune any stale reflogs (enabled by default)
8. `--no-stale-fix`: Do not prune stale reflogs
9. `-n <number>, --max-count=<number>`: Limit the number of entries to show

### Show Subcommand Options

10. `--format=<format>`: Specify the output format
11. `--date=<format>`: Specify the date format
12. `--exclude-existing`: Don't show existing refs
13. `--single-worktree`: Only accept a single worktree
14. `--verbose`: Include extra information in the output

### Expire Subcommand Options

15. `--expire=<time>`: Prune entries older than the specified time
16. `--expire-unreachable=<time>`: Prune unreachable entries older than the specified time
17. `--all`: Process the reflogs of all references
18. `--dry-run`: Do not actually prune any entries
19. `--verbose`: Print extra information on screen
20. `--stale-fix`: Prune any stale reflogs (default)
21. `--rewrite`: Rewrite the SHA-1s of reflog entries

### Delete Subcommand Options

22. `--rewrite`: Rewrite the SHA-1s of reflog entries
23. `--updateref`: Update the ref with the SHA-1 of the top reflog entry

## Examples

1. Show the reflog for HEAD:
   ```
   git reflog
   ```

2. Show the reflog for a specific branch:
   ```
   git reflog show feature-branch
   ```

3. Show a limited number of reflog entries:
   ```
   git reflog -n 5
   ```

4. Show reflog with custom date format:
   ```
   git reflog --date=iso
   ```

5. Expire reflog entries older than 90 days:
   ```
   git reflog expire --expire=90.days.ago
   ```

6. Delete a specific reflog entry:
   ```
   git reflog delete HEAD@{2}
   ```

7. Check if a reflog exists for a reference:
   ```
   git reflog exists feature-branch
   ```

## Use Cases

1. **Recovering lost commits**: If you accidentally reset or delete a commit, you can use reflog to find and restore it.

2. **Undoing changes**: Reflog allows you to go back to any previous state of your project, even if you've made multiple changes.

3. **Debugging**: Reflog can help you understand how your repository reached its current state.

4. **Branch recovery**: If you accidentally delete a branch, you can use reflog to find the last commit of that branch and recreate it.

Remember, reflog is a local record and is not pushed to remote repositories. It's a powerful tool for recovering from mistakes, but it should be used carefully, especially when rewriting history or deleting entries.
