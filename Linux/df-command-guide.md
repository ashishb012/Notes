# df Command Guide: Options and Examples

The `df` (disk free) command in Linux is used to display information about disk space usage on file systems. Its basic syntax is:

```
df [OPTIONS] [FILE]...
```

## Common Options

1. `-h` or `--human-readable`: Print sizes in human-readable format (e.g., 1K, 234M, 2G)
2. `-i` or `--inodes`: List inode information instead of block usage
3. `-T` or `--print-type`: Print file system type
4. `-a` or `--all`: Include dummy file systems
5. `-x` or `--exclude-type=TYPE`: Exclude file systems of TYPE
6. `-t` or `--type=TYPE`: Limit listing to file systems of TYPE
7. `-k`: Use 1K-byte blocks (default)
8. `-m`: Use 1M-byte blocks
9. `--total`: Produce a grand total
10. `-P` or `--portability`: Use POSIX output format
11. `-l` or `--local`: Limit listing to local file systems

## Examples

1. Basic usage (display disk space for all mounted file systems):
   ```
   df
   ```

2. Display in human-readable format:
   ```
   df -h
   ```
   This shows sizes in KB, MB, GB, etc.

3. Show inode information:
   ```
   df -i
   ```
   This displays inode usage instead of block usage.

4. Display file system type:
   ```
   df -T
   ```
   This shows the type of each file system along with usage information.

5. Show information for a specific file or directory:
   ```
   df -h /home
   ```
   This displays disk usage information for the file system containing `/home`.

6. Exclude certain file system types:
   ```
   df -x tmpfs -x devtmpfs
   ```
   This shows disk usage for all file systems except `tmpfs` and `devtmpfs`.

7. Show only specific file system types:
   ```
   df -t ext4 -t xfs
   ```
   This displays information only for ext4 and xfs file systems.

8. Display grand total:
   ```
   df -h --total
   ```
   This shows disk usage for all file systems and adds a total at the end.

9. Use megabyte blocks:
   ```
   df -m
   ```
   This displays sizes in 1M-byte blocks.

10. Show only local file systems:
    ```
    df -l
    ```
    This excludes network file systems.

11. Combine multiple options:
    ```
    df -hT --total -x tmpfs
    ```
    This shows human-readable output with file system types, excludes tmpfs, and includes a total.

12. POSIX output format:
    ```
    df -P
    ```
    This uses the POSIX output format, which is more standardized and portable.

13. Show all file systems, including dummy ones:
    ```
    df -a
    ```
    This includes file systems that are usually not shown (like `/proc`).

Important Notes:
- The output of `df` can vary depending on the system and mounted file systems.
- Without any options, `df` uses 1K-byte blocks by default.
- The `-h` option is very commonly used as it makes the output much more readable.
- `df` shows the space used by mounted file systems; for detailed directory usage, use the `du` command.
- Root privileges may be required to see information for certain file systems.

