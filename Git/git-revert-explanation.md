# Git Revert Command

The `git revert` command is used to create new commits that undo the changes made by previous commits. Unlike `git reset`, which modifies the existing Git history, `revert` creates new commits and is safe to use on public branches.

## Basic Usage

```
git revert <commit>
```

This creates a new commit that undoes the changes introduced by the specified commit.

## Common Options

1. `git revert -e` or `git revert --edit`
   - Edit the commit message prior to committing the revert.

2. `git revert -n` or `git revert --no-commit`
   - Revert the changes without automatically creating a new commit. The changes are added to the staging area.

3. `git revert --no-edit`
   - Revert and create the new commit without opening an editor for the commit message.

4. `git revert -m <parent-number>` or `git revert --mainline <parent-number>`
   - When reverting a merge commit, specify which parent should be considered the mainline.

5. `git revert --continue`
   - Continue the revert operation after resolving conflicts.

6. `git revert --abort`
   - Cancel the revert operation and return to the pre-revert state.

7. `git revert --quit`
   - Forget about the current revert operation. Can be used to clear the sequencer state after resolving conflicts.

## Advanced Options

8. `git revert --strategy=<strategy>`
   - Use the given merge strategy.

9. `git revert --strategy-option=<option>`
   - Pass the merge strategy-specific option to the merge strategy.

10. `git revert --gpg-sign[=<key-id>]`
    - GPG-sign commits.

11. `git revert --signoff`
    - Add a Signed-off-by trailer to the commit message.

12. `git revert --reference`
    - Append ref names and hashes to the commit message.

13. `git revert --rerere-autoupdate`
    - Allow rerere to update the index with the result of auto-conflict resolution if possible.

## Examples

1. Revert the last commit:
   ```
   git revert HEAD
   ```

2. Revert a specific commit:
   ```
   git revert abc1234
   ```

3. Revert multiple commits:
   ```
   git revert HEAD~3..HEAD
   ```

4. Revert a merge commit:
   ```
   git revert -m 1 <merge-commit-hash>
   ```

5. Revert a commit without immediately committing the result:
   ```
   git revert -n <commit-hash>
   ```

6. Revert a commit and edit the commit message:
   ```
   git revert -e <commit-hash>
   ```

7. Revert multiple commits in reverse chronological order:
   ```
   git revert HEAD~2^..HEAD
   ```

## Notes and Best Practices

- `git revert` is generally safer than `git reset` for undoing changes in public branches because it doesn't alter existing history.
- When reverting merge commits, you must specify which parent is the mainline using the `-m` option.
- If you encounter conflicts during a revert, resolve them as you would with a merge conflict, then use `git revert --continue`.
- For a series of bad commits, it's often easier to revert them one by one from newest to oldest (to avoid conflicts) or to use the range syntax.
- Remember that reverting a revert effectively reapplies the original commit.
- If you just want to inspect the changes that would be reverted without actually reverting, you can use `git show <commit>` instead.

Remember, while `git revert` is safer than some alternatives, it's always a good idea to ensure you have a clean working directory and that you understand which changes will be reverted before proceeding.
