# Git Push Command

The `git push` command is used to upload local repository content to a remote repository. It transfers commits from your local repository to a remote repo.

## Basic Usage

```
git push <remote> <branch>
```

This pushes the specified branch to the specified remote.

## Common Options

1. `git push -u <remote> <branch>` or `git push --set-upstream <remote> <branch>`
   - Sets the upstream branch for the current local branch.

2. `git push -f` or `git push --force`
   - Forces the push even if it results in a non-fast-forward merge. Use with caution!

3. `git push --all`
   - Push all branches.

4. `git push --tags`
   - Push all tags.

5. `git push <remote> --delete <branch>`
   - Delete a remote branch.

6. `git push -v` or `git push --verbose`
   - Run verbosely.

7. `git push --dry-run`
   - Do everything except actually send the updates.

8. `git push --prune`
   - Remove remote branches that don't have a local counterpart.

9. `git push --mirror`
   - Push all refs under refs/heads/, refs/remotes/, and refs/tags/.

10. `git push --atomic`
    - Push all refs in one atomic transaction. If any ref fails to update, no refs will be updated.

11. `git push --follow-tags`
    - Push all the refs that would be pushed without this option, and also push annotated tags that are missing.

12. `git push --force-with-lease`
    - Allows you to force push only if the remote hasn't been modified since your last fetch.

## Advanced Options

1. `--recurse-submodules=check|on-demand|no`
   - Controls recursive pushing of submodules.

2. `--thin`
   - Use thin pack (smaller pack at the cost of server CPU time).

3. `--receive-pack=<git-receive-pack>`
   - Specify a custom receive pack program.

4. `--repo=<repository>`
   - This option is equivalent to the <repository> argument.

## Examples

1. Push a specific branch to the remote:
   ```
   git push origin main
   ```

2. Set the upstream branch and push:
   ```
   git push -u origin feature-branch
   ```

3. Force push (use with caution):
   ```
   git push -f origin main
   ```

4. Push all tags:
   ```
   git push --tags
   ```

5. Delete a remote branch:
   ```
   git push origin --delete old-feature
   ```

6. Push all branches:
   ```
   git push --all origin
   ```

7. Force push with a safety check:
   ```
   git push --force-with-lease origin main
   ```

Remember, `git push` is a crucial command for sharing your work with others. Always be cautious when using force options, as they can overwrite changes on the remote repository.
