# Git Fetch Command

The `git fetch` command downloads commits, files, and refs from a remote repository into your local repo. It's used to see what others have been working on without merging those changes into your local branches.

## Basic Syntax

```
git fetch [<options>] [<repository> [<refspec>...]]
```

## Common Options

1. `--all`: Fetch all remotes.
2. `--append` or `-a`: Append ref names and object names of fetched refs to the existing contents of `.git/FETCH_HEAD`.
3. `--atomic`: Use an atomic transaction to update local refs. Either all refs are updated, or on error, no refs are updated.
4. `--depth=<depth>`: Limit fetching to the specified number of commits from the tip of each remote branch history.
5. `--deepen=<depth>`: Similar to --depth, but deepen the history of a shallow repository.
6. `--shallow-since=<date>`: Deepen or shorten the history by date.
7. `--shallow-exclude=<revision>`: Deepen or shorten the history by excluding commits reachable from a specified remote branch or tag.
8. `--unshallow`: Convert a shallow repository to a complete one.
9. `--update-shallow`: Update .git/shallow for fetched refs.
10. `--negotiation-tip=<commit|glob>`: Specify which commit/glob to report while fetching to the server.
11. `--negotiate-only`: Do not fetch, only print common ancestors.
12. `--dry-run`: Show what would be done, without making any changes.
13. `--write-fetch-head`: Write the list of remote refs fetched in the FETCH_HEAD file. (Default behavior)
14. `--no-write-fetch-head`: Do not write the FETCH_HEAD file.
15. `--force` or `-f`: Force overwriting of local reference.
16. `--keep`: Keep downloaded pack.
17. `--multiple`: Allow several <repository> and <group> arguments.
18. `--auto-maintenance`: Run 'git maintenance run --auto' at the end (default).
19. `--no-auto-maintenance`: Don't run 'git maintenance' at the end.
20. `--auto-gc`: Run 'git gc --auto' after fetching.
21. `--no-auto-gc`: Don't run 'git gc --auto' after fetching.
22. `--write-commit-graph`: Write a commit-graph after fetching.
23. `--no-write-commit-graph`: Don't write a commit-graph after fetching.
24. `--prefetch`: Modify the refspec to place all refs within refs/prefetch/.
25. `--prune`: Remove any remote-tracking references that no longer exist on the remote.
26. `--prune-tags`: Remove any local tags that no longer exist on the remote if --prune is enabled.
27. `--no-tags`: Don't fetch tags.
28. `--refmap=<refspec>`: Use this refspec to map refs to remote-tracking branches.
29. `--tags`: Fetch all tags and associated objects.
30. `--recurse-submodules[=yes|on-demand|no]`: Fetch new commits of populated submodules.
31. `--jobs=<n>` or `-j <n>`: Number of parallel children to be used for fetching submodules.
32. `--no-recurse-submodules`: Disable recursive fetching of submodules.
33. `--set-upstream`: Set upstream for git pull/fetch.
34. `--submodule-prefix=<path>`: Prepend <path> to paths printed in informative messages.
35. `--upload-pack <upload-pack>`: Specify path to upload pack on remote end.
36. `--quiet` or `-q`: Suppress all output.
37. `--verbose` or `-v`: Be verbose.
38. `--progress`: Force progress reporting.

## Examples

1. Fetch from all remotes:
   ```
   git fetch --all
   ```

2. Fetch from a specific remote:
   ```
   git fetch origin
   ```

3. Fetch a specific branch:
   ```
   git fetch origin main
   ```

4. Fetch and prune:
   ```
   git fetch --prune origin
   ```

5. Fetch all tags:
   ```
   git fetch --tags
   ```

6. Fetch with a depth limit:
   ```
   git fetch --depth=1 origin
   ```

Remember, `git fetch` only downloads new data from a remote repository - it doesn't integrate any of this new data into your working files. Fetch is a safe way to review commits before integrating them with your local repository.
