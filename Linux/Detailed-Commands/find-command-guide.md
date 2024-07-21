# find Command Guide: Options and Examples

The `find` command in Unix and Linux is used to search for files and directories in a directory hierarchy. Its basic syntax is:

```
find [path...] [expression]
```

## Common Options and Tests

1. `-name pattern`: Search for files and directories that match the given pattern
2. `-type t`: Search for files of a specific type (f: regular file, d: directory, l: symbolic link)
3. `-size n[cwbkMG]`: Search for files based on size (c: bytes, w: 2-byte words, b: 512-byte blocks, k: kilobytes, M: megabytes, G: gigabytes)
4. `-mtime n`: Search for files modified n days ago
5. `-atime n`: Search for files accessed n days ago
6. `-ctime n`: Search for files with changed status n days ago
7. `-newer file`: Search for files newer than the specified file
8. `-user name`: Search for files owned by a specific user
9. `-group name`: Search for files belonging to a specific group
10. `-perm mode`: Search for files with specific permissions
11. `-maxdepth levels`: Descend at most levels of directories below the command line arguments
12. `-mindepth levels`: Do not apply any tests or actions at levels less than levels
13. `-empty`: Search for empty files and directories
14. `-exec command {} +`: Execute a command on each found file/directory

## Examples

1. Basic usage - find all files in current directory and subdirectories:
   ```
   find .
   ```

2. Find files by name:
   ```
   find /home/user -name "*.txt"
   ```
   This finds all `.txt` files in the `/home/user` directory and its subdirectories.

3. Find directories:
   ```
   find /home/user -type d
   ```
   This finds all directories under `/home/user`.

4. Find files by size:
   ```
   find / -size +100M
   ```
   This finds files larger than 100 megabytes.

5. Find files modified in the last 7 days:
   ```
   find /home/user -mtime -7
   ```

6. Find files accessed more than 30 days ago:
   ```
   find /home/user -atime +30
   ```

7. Find files with specific permissions:
   ```
   find /home/user -perm 644
   ```
   This finds files with exact permissions 644 (rw-r--r--).

8. Find empty files:
   ```
   find /home/user -type f -empty
   ```

9. Find and delete files:
   ```
   find /home/user -name "*.tmp" -delete
   ```
   This finds and deletes all `.tmp` files. Use with caution!

10. Find and execute a command:
    ```
    find /home/user -name "*.jpg" -exec convert {} {}.png \;
    ```
    This finds all `.jpg` files and converts them to `.png` using the `convert` command.

11. Find files and change their permissions:
    ```
    find /home/user -type f -exec chmod 644 {} +
    ```
    This changes the permissions of all regular files to 644.

12. Find files newer than a specific file:
    ```
    find /home/user -newer /home/user/reference_file
    ```

13. Find with multiple conditions (AND):
    ```
    find /home/user -type f -name "*.log" -size +1M
    ```
    This finds log files larger than 1 megabyte.

14. Find with multiple conditions (OR):
    ```
    find /home/user -type f \( -name "*.jpg" -o -name "*.png" \)
    ```
    This finds files with either .jpg or .png extensions.

15. Find and output with custom format:
    ```
    find /home/user -type f -printf "%p - %s bytes\n"
    ```
    This prints each file's path and size.

Remember to use `find` carefully, especially when combined with commands that modify or delete files. Always test your commands on a small subset of data first, particularly when using options like `-delete` or `-exec`.
