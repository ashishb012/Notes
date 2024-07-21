# whereis Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `whereis` command in Unix and Linux systems is used to locate the binary, source, and manual page files for a specified command. Its basic syntax is:

```
whereis [options] name ...
```

## Common Options

1. `-b`: Search for binaries only
2. `-m`: Search for manual pages only
3. `-s`: Search for sources only
4. `-u`: Search for unusual entries (files that do not have expected extensions or locations)
5. `-B list`: Limit the search for binaries to the specified list of directories
6. `-M list`: Limit the search for manual pages to the specified list of directories
7. `-S list`: Limit the search for sources to the specified list of directories
8. `-f`: Terminate the directory list for `-B`, `-M`, or `-S`
9. `-l`: Output effective lookup paths

## Examples

1. Basic usage - find all related files for a command:
   ```
   whereis ls
   ```
   This might output: `ls: /bin/ls /usr/share/man/man1/ls.1.gz`

2. Search for binary only:
   ```
   whereis -b python
   ```
   This will only show the path to the Python executable(s).

3. Search for manual pages only:
   ```
   whereis -m gcc
   ```
   This will show the paths to the manual pages for gcc.

4. Search for source files only:
   ```
   whereis -s bash
   ```
   This will attempt to locate source files for bash.

5. Find unusual entries:
   ```
   whereis -u *
   ```
   This will list files in standard binary directories that don't have standard extensions.

6. Combine options:
   ```
   whereis -bm python
   ```
   This will find both binary and manual page locations for Python.

7. Specify search paths for binaries:
   ```
   whereis -B /usr/bin /usr/local/bin -f ls
   ```
   This limits the binary search to the specified directories.

8. Specify search paths for manual pages:
   ```
   whereis -M /usr/share/man -f -m bash
   ```
   This searches for bash manual pages only in the specified directory.

9. Search for multiple commands:
   ```
   whereis python bash ls
   ```
   This will show locations for all specified commands.

10. Show effective lookup paths:
    ```
    whereis -l
    ```
    This displays the directories that `whereis` searches by default.

11. Combine with other commands:
    ```
    whereis -b python | cut -d: -f2 | xargs ls -l
    ```
    This finds the Python binary and then lists its details using `ls -l`.

12. Use in a script to check for command existence:
    ```bash
    if whereis -b python >/dev/null 2>&1; then
        echo "Python is installed"
    else
        echo "Python is not installed"
    fi
    ```

Remember that `whereis` is designed to find standard locations for binaries, manual pages, and source files. It may not find files located in non-standard directories or custom installations. For a more comprehensive search, you might need to use commands like `find` or `locate`.

Also, the behavior and available options of `whereis` can vary slightly between different Unix-like systems. Always check the man pages (`man whereis`) on your specific system for the most accurate information.

[Back to Linux Commands](../readme.md)
