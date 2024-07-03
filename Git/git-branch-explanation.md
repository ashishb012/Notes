# Git Branch Command

The `git branch` command lets you create, list, rename, and delete branches. It's a key part of the Git workflow, allowing parallel lines of development.

## Basic Usage

```
git branch
```

This lists all local branches in the current repository.

## Common Options

1. `git branch <branch-name>`
   - Creates a new branch with the given name.

2. `git branch -d <branch-name>` or `git branch --delete <branch-name>`
   - Deletes the specified branch. Use -D for force delete.

3. `git branch -m <old-name> <new-name>` or `git branch --move <old-name> <new-name>`
   - Renames a branch.

4. `git branch -a` or `git branch --all`
   - Lists all branches, both local and remote.

5. `git branch -r` or `git branch --remotes`
   - Lists or deletes (-d) remote-tracking branches.

6. `git branch -v` or `git branch --verbose`
   - Shows SHA1 and commit subject line for each head.

7. `git branch --merged`
   - Lists branches that have been merged into the current branch.

8. `git branch --no-merged`
   - Lists branches that have not been merged into the current branch.

9. `git branch --contains <commit>`
   - Shows branches that contain the specified commit.

10. `git branch --show-current`
    - Prints the name of the current branch.

## Advanced Options

1. `git branch --set-upstream-to=<remote>/<branch>`
   - Sets up tracking information for the current branch.

2. `git branch --unset-upstream`
   - Removes the upstream information for the current branch.

3. `git branch --edit-description`
   - Opens an editor to change the description of the current branch.

4. `git branch --color[=<when>]`
   - Use colored output. <when> can be always, never, or auto.

5. `git branch --no-color`
   - Turn off branch colors, even when the terminal supports it.

6. `git branch --column[=<options>]`
   - Display branch listing in columns.

7. `git branch --sort=<key>`
   - Sort branches by the given key.

## Examples

1. Create a new branch:
   ```
   git branch feature-branch
   ```

2. Delete a branch:
   ```
   git branch -d old-feature
   ```

3. Rename a branch:
   ```
   git branch -m old-name new-name
   ```

4. List all branches with verbose information:
   ```
   git branch -av
   ```

5. Show branches that contain a specific commit:
   ```
   git branch --contains 1234abc
   ```

6. Set upstream for the current branch:
   ```
   git branch --set-upstream-to=origin/main
   ```

7. List merged branches:
   ```
   git branch --merged
   ```

Remember, `git branch` by itself only creates or lists branches. To switch to a branch, you need to use `git checkout` or `git switch`. The command `git checkout -b <new-branch>` is a shortcut to create a new branch and switch to it immediately.
