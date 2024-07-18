# rm Command Guide

[Back to Linux Commands](../readme.md)

The `rm` command is used to remove (delete) files and directories in Unix and Unix-like operating systems. It's a powerful command that should be used with caution, as it can lead to permanent data loss.

## Basic Syntax

```
rm [OPTION]... [FILE]...
```

## Warning

**Be extremely careful when using `rm`, especially with wildcards or the `-r` option. There is no "trash bin" or easy way to recover files deleted with `rm`. Always double-check your command before pressing Enter.**

## Common Options

1. `-f, --force`: Ignore nonexistent files and arguments, never prompt
2. `-i`: Prompt before every removal
3. `-I`: Prompt once before removing more than three files, or when removing recursively
4. `-r, -R, --recursive`: Remove directories and their contents recursively
5. `-d, --dir`: Remove empty directories
6. `-v, --verbose`: Explain what is being done
7. `--preserve-root`: Do not remove '/' (default)
8. `--no-preserve-root`: Do not treat '/' specially
9. `--one-file-system`: When removing a hierarchy recursively, skip any directory on a different file system
10. `--help`: Display help information and exit
11. `--version`: Output version information and exit

## Examples

1. Remove a single file:
   ```
   rm file.txt
   ```

2. Remove multiple files:
   ```
   rm file1.txt file2.txt file3.txt
   ```

3. Remove a file with confirmation prompt:
   ```
   rm -i important_file.txt
   ```

4. Remove files forcefully (no prompt, ignore nonexistent files):
   ```
   rm -f unnecessary_file.txt
   ```

5. Remove an empty directory:
   ```
   rm -d empty_directory
   ```

6. Remove a directory and its contents recursively:
   ```
   rm -r directory_name
   ```

7. Remove a directory and its contents forcefully:
   ```
   rm -rf directory_name
   ```

8. Remove files verbosely (show what's being done):
   ```
   rm -v *.log
   ```

9. Remove files with a specific extension:
   ```
   rm *.tmp
   ```

10. Remove files interactively when removing more than 3 files or recursively:
    ```
    rm -I *.txt
    ```

11. Remove files with spaces in the name:
    ```
    rm "file with spaces.txt"
    ```

12. Remove files starting with a hyphen:
    ```
    rm -- -file-starting-with-hyphen.txt
    ```

13. Remove files while preserving root directory:
    ```
    rm --preserve-root -rf /path/to/directory
    ```

14. Remove all files in current directory (be very careful!):
    ```
    rm *
    ```

15. Use rm with find to remove files based on certain criteria:
    ```
    find . -type f -name "*.tmp" -exec rm {} +
    ```

## Safety Tips

1. Always double-check your rm commands before executing them.
2. Use the `-i` option when you're unsure about the files you're deleting.
3. Be extremely careful with wildcards (*) and the `-r` option.
4. Consider using safer alternatives like `trash-cli` for everyday use.
5. Regularly backup important data to prevent accidental loss.

Remember to always consult the manual (`man rm`) or use `rm --help` for the most up-to-date and system-specific information, as options may vary slightly between different Unix-like systems.

[Back to Linux Commands](../readme.md)
