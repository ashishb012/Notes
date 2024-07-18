# rmdir Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `rmdir` (remove directory) command in Linux is used to delete empty directories. Its basic syntax is:

```
rmdir [OPTIONS] DIRECTORY...
```

## Options

The `rmdir` command has fewer options compared to many other Linux commands, but they are still useful:

1. `-p` or `--parents`: Remove DIRECTORY and its ancestors. E.g., `rmdir -p a/b/c` is similar to `rmdir a/b/c a/b a`.
2. `-v` or `--verbose`: Output a diagnostic for every directory processed.
3. `--ignore-fail-on-non-empty`: Ignore each failure that is solely because a directory is non-empty.

## Examples

1. Basic usage (remove a single empty directory):
   ```
   rmdir empty_directory
   ```
   This removes the directory named `empty_directory` if it's empty.

2. Remove multiple directories:
   ```
   rmdir dir1 dir2 dir3
   ```
   This removes `dir1`, `dir2`, and `dir3` if they are all empty.

3. Remove parent directories:
   ```
   rmdir -p parent/child/grandchild
   ```
   This removes `grandchild`, then `child`, then `parent`, assuming each is empty after the contained directory is removed.

4. Verbose removal:
   ```
   rmdir -v empty_directory
   ```
   This removes `empty_directory` and outputs a message about what it's doing.

5. Ignore failures on non-empty directories:
   ```
   rmdir --ignore-fail-on-non-empty dir1 dir2 dir3
   ```
   This attempts to remove `dir1`, `dir2`, and `dir3`, but doesn't report an error if any of them are not empty.

6. Combine options:
   ```
   rmdir -pv parent/child/grandchild
   ```
   This removes the nested directories, starting from `grandchild`, and provides verbose output for each removal.

7. Using with wildcard (be careful!):
   ```
   rmdir test_*/
   ```
   This removes all empty directories that start with `test_`.

Important Notes:
- `rmdir` will only remove empty directories. If a directory contains any files or subdirectories, `rmdir` will fail.
- For removing non-empty directories, you typically use the `rm -r` command instead.
- Always double-check before using `rmdir`, especially with wildcards, to avoid unintended deletions.
- If you need to remove a directory and all its contents, regardless of whether it's empty, use `rm -r` instead of `rmdir`.

[Back to Linux Commands](../readme.md)
