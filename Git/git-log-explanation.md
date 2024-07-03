# Git Log Command

The `git log` command displays the commit history of a repository. It's a powerful tool for understanding the evolution of a project and for finding specific changes.

## Basic Syntax

```
git log [<options>] [<revision range>] [[--] <path>...]
```

## Common Options

### Commit Limiting Options

1. `-<number>, -n <number>, --max-count=<number>`: Limit the number of commits to output.
2. `--skip=<number>`: Skip number commits before starting to show the commit output.
3. `--since=<date>, --after=<date>`: Show commits more recent than a specific date.
4. `--until=<date>, --before=<date>`: Show commits older than a specific date.
5. `--author=<pattern>, --committer=<pattern>`: Limit the commits to ones with author/committer header lines that match the specified pattern.
6. `--grep=<pattern>`: Limit the commits to ones with log messages that match the specified pattern.
7. `--all-match`: Limit the commits to ones that match all given --grep, --author and --committer instead of ones that match at least one.
8. `--no-merges`: Do not print commits with more than one parent.
9. `--merges`: Print only merge commits.
10. `--first-parent`: Follow only the first parent commit upon seeing a merge commit.

### History Simplification Options

11. `--full-history`: Do not remove some history entries to find the simplified history.
12. `--dense`: Only display selected commits, plus meaningful predecessors.
13. `--sparse`: Display all commits in the simplified history.
14. `--simplify-merges`: Additional option to --full-history to remove some needless merges from the resulting history.
15. `--ancestry-path`: Only display commits that exist directly on the ancestry chain between the "from" and "to" commits in the given revision range.

### Commit Ordering Options

16. `--date-order`: Sort commits by date when possible.
17. `--author-date-order`: Sort commits by author date when possible.
18. `--topo-order`: Sort commits topologically.
19. `--reverse`: Output the commits in reverse order.

### Formatting Options

20. `--pretty[=<format>], --format=<format>`: Pretty-print the contents of the commit logs in a given format.
21. `--abbrev-commit`: Show only a partial prefix of the full 40-byte hexadecimal object name.
22. `--no-abbrev-commit`: Show the full 40-byte hexadecimal commit object name.
23. `--oneline`: Shorthand for "--pretty=oneline --abbrev-commit".
24. `--encoding=<encoding>`: Re-code the commit log messages in the encoding.
25. `--notes[=<ref>]`: Show the notes that annotate the commit.

### Diff Options

26. `-p, -u, --patch`: Generate patch.
27. `--stat`: Generate a diffstat.
28. `--shortstat`: Output only the last line of the --stat format containing total number of modified files, as well as number of added and deleted lines.
29. `--name-only`: Show only names of changed files.
30. `--name-status`: Show only names and status of changed files.

### Other Options

31. `--graph`: Draw a text-based graphical representation of the commit history on the left hand side of the output.
32. `--decorate[=short|full|auto|no]`: Print out the ref names of any commits that are shown.
33. `--color[=<when>]`: Show colored diff.
34. `--walk-reflogs`: Instead of walking the commit ancestry chain, walk reflog entries from the most recent one to older ones.
35. `--follow`: Continue listing the history of a file beyond renames.

## Examples

1. Basic log:
   ```
   git log
   ```

2. Show only the last 5 commits:
   ```
   git log -5
   ```

3. Show commits in a specific date range:
   ```
   git log --since="2023-01-01" --until="2023-12-31"
   ```

4. Show commits by a specific author:
   ```
   git log --author="John Doe"
   ```

5. Show a graph of commits:
   ```
   git log --graph --oneline --decorate
   ```

6. Show changes in each commit:
   ```
   git log -p
   ```

7. Show statistics for changed files:
   ```
   git log --stat
   ```

8. Show commits that changed a specific file:
   ```
   git log -- path/to/file
   ```

9. Show commit history in a custom format:
   ```
   git log --pretty=format:"%h - %an, %ar : %s"
   ```

10. Show merge commits only:
    ```
    git log --merges
    ```

Remember, `git log` is a versatile command with many options that can be combined to create powerful custom views of your repository's history. Experiment with different combinations to find what works best for your workflow.
