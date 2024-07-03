# Git Commit Command

The `git commit` command creates a new commit containing the current contents of the index and the given log message describing the changes.

## Basic Usage

```
git commit -m "Commit message"
```

This creates a new commit with the staged changes and the specified commit message.

## Common Options

1. `git commit -a` or `git commit --all`
   - Automatically stage files that have been modified and deleted, but new files you have not told Git about are not affected.

2. `git commit -m <msg>` or `git commit --message=<msg>`
   - Use the given `<msg>` as the commit message.

3. `git commit -am <msg>`
   - Combination of `-a` and `-m`. Stages all changes to tracked files and commits with the given message.

4. `git commit --amend`
   - Replace the tip of the current branch by creating a new commit.

5. `git commit -v` or `git commit --verbose`
   - Show unified diff between the HEAD commit and what would be committed at the bottom of the commit message template.

6. `git commit --no-verify`
   - This option bypasses the pre-commit and commit-msg hooks.

7. `git commit -s` or `git commit --signoff`
   - Adds a Signed-off-by line at the end of the commit message.

8. `git commit --author=<author>`
   - Override the commit author. Specify an explicit author using the standard `A U Thor <author@example.com>` format.

9. `git commit --date=<date>`
   - Override the author date used in the commit.

10. `git commit --allow-empty`
    - Usually recording a commit that has the exact same tree as its sole parent commit is a mistake. This option bypasses the safety.

11. `git commit --no-edit`
    - Use the selected commit message without launching an editor.

12. `git commit --dry-run`
    - Don't actually create a commit, just show a list of paths that are to be committed.

## Examples

1. Create a simple commit:
   ```
   git commit -m "Add new feature"
   ```

2. Commit all changes to tracked files:
   ```
   git commit -a -m "Update all tracked files"
   ```

3. Amend the last commit:
   ```
   git commit --amend -m "Updated commit message"
   ```

4. Create a commit with a multi-line message:
   ```
   git commit -m "Short summary" -m "Longer description of the changes"
   ```

5. Create a signed commit:
   ```
   git commit -s -m "Signed commit"
   ```

Remember, `git commit` creates a new commit with the changes you've staged using `git add`. If you haven't staged any changes, `git commit` will not do anything unless you use the `-a` option.
