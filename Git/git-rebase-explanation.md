# Git Rebase Command

The `git rebase` command is used to change the base of your branch from one commit to another, making it appear as if you'd created your branch from a different commit. Rebasing is a way to integrate changes from one branch into another.

## Basic Usage

```
git rebase <base>
```

This changes the base of your current branch to the specified `<base>`.

## Common Options

1. `git rebase -i <base>` or `git rebase --interactive <base>`
   - Starts an interactive rebase session, allowing you to edit, squash, or drop commits.

2. `git rebase --continue`
   - Continues the rebase operation after resolving conflicts.

3. `git rebase --abort`
   - Aborts the rebase operation and returns the branch to its original state.

4. `git rebase --skip`
   - Skips the current commit and continues with the next one.

5. `git rebase --onto <newbase> <oldbase> <branch>`
   - Rebase `<branch>` onto `<newbase>`, starting from `<oldbase>`.

6. `git rebase --exec <cmd>`
   - Executes shell commands for each commit during the rebase.

7. `git rebase --keep-empty`
   - Keeps empty commits during the rebase.

8. `git rebase --no-ff`
   - Creates a merge commit even if a fast-forward is possible.

## Advanced Options

9. `git rebase --merge`
   - Uses merging strategies to rebase.

10. `git rebase --strategy=<strategy>`
    - Uses the given merge strategy.

11. `git rebase --strategy-option=<option>`
    - Passes the merge strategy-specific option to the merge strategy.

12. `git rebase --whitespace=<option>`
    - Specifies how to handle whitespace errors.

13. `git rebase --root`
    - Rebase all commits reachable from the current branch.

14. `git rebase --autosquash`
    - Automatically squash commits marked as "fixup" or "squash".

15. `git rebase --gpg-sign[=<key-id>]`
    - GPG-sign commits.

16. `git rebase --quiet` or `git rebase -q`
    - Suppress output.

## Examples

1. Rebase the current branch onto the main branch:
   ```
   git rebase main
   ```

2. Interactive rebase of the last 3 commits:
   ```
   git rebase -i HEAD~3
   ```

3. Rebase a specific branch onto main:
   ```
   git rebase main feature-branch
   ```

4. Rebase onto a specific commit:
   ```
   git rebase --onto <newbase> <oldbase> <branch>
   ```

5. Autosquash commits during an interactive rebase:
   ```
   git rebase -i --autosquash main
   ```

6. Rebase all commits in the current branch:
   ```
   git rebase --root -i
   ```

## Notes and Best Practices

- Rebasing rewrites commit history. It's generally not recommended to rebase commits that have been pushed to a public repository.
- Always create a backup branch before performing a complex rebase.
- When rebasing, you're essentially replaying commits on top of the new base. This can lead to conflicts that need to be resolved manually.
- Interactive rebasing (`-i`) is a powerful tool for cleaning up your commit history before merging or pushing.
- The `--onto` option is particularly useful for moving a topic branch to a different base.
- Be cautious when using `--root`, as it rebases all commits in your repository's history.
- If you encounter conflicts during a rebase, resolve them in each file, stage the changes, and then use `git rebase --continue`.
- Remember that a rebase operation may need to be force-pushed (`git push --force-with-lease`) if the branch has already been pushed to a remote repository.

Rebasing can be a complex operation, especially for beginners. It's important to understand its implications fully before using it, particularly on shared branches.
