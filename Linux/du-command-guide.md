# du Command Guide: Options and Examples

The `du` (disk usage) command in Linux is used to estimate file and directory space usage. Its basic syntax is:

```
du [OPTIONS] [FILE]...
```

## Common Options

1. `-h` or `--human-readable`: Print sizes in human-readable format (e.g., 1K, 234M, 2G)
2. `-s` or `--summarize`: Display only a total for each argument
3. `-c` or `--total`: Produce a grand total
4. `-a` or `--all`: Write counts for all files, not just directories
5. `-d N` or `--max-depth=N`: Print the total for a directory only if it is N or fewer levels below the command line argument
6. `-b` or `--bytes`: Print size in bytes
7. `-k`: Print size in kilobytes (1024 bytes)
8. `-m`: Print size in megabytes
9. `--apparent-size`: Print apparent sizes, rather than disk usage
10. `-L` or `--dereference`: Dereference all symbolic links
11. `-S` or `--separate-dirs`: For directories, do not include size of subdirectories
12. `--exclude=PATTERN`: Exclude files that match PATTERN
13. `--time`: Show time of last modification of any file in the directory

## Examples

1. Basic usage (display disk usage for current directory):
   ```
   du
   ```

2. Display in human-readable format:
   ```
   du -h
   ```
   This shows sizes in KB, MB, GB, etc.

3. Summarize disk usage of a directory:
   ```
   du -sh /home/user
   ```
   This shows the total size of `/home/user` in human-readable format.

4. Show disk usage for all files, not just directories:
   ```
   du -ah /path/to/directory
   ```
   This displays the size of each file and directory.

5. Limit depth of reporting:
   ```
   du -h --max-depth=2 /path/to/directory
   ```
   This shows disk usage up to 2 levels deep in the directory structure.

6. Show total disk usage:
   ```
   du -ch /path/to/directory
   ```
   This displays usage for each item and a total at the end.

7. Sort output by size:
   ```
   du -h /path/to/directory | sort -h
   ```
   This sorts the output from smallest to largest. Use `sort -rh` for reverse order.

8. Show only total disk usage in bytes:
   ```
   du -sb /path/to/directory
   ```
   This displays the total size in bytes.

9. Exclude certain files or directories:
   ```
   du -h --exclude='*.txt' /path/to/directory
   ```
   This excludes all .txt files from the calculation.

10. Show apparent size instead of disk usage:
    ```
    du -h --apparent-size /path/to/file
    ```
    This shows the apparent size, which might differ from disk usage due to sparse files or compression.

11. Show disk usage with last modification time:
    ```
    du -h --time /path/to/directory
    ```
    This includes the last modification time for each file/directory.

12. Don't follow symbolic links:
    ```
    du -h --no-dereference /path/with/symlinks
    ```
    This doesn't follow symbolic links when calculating disk usage.

13. Show disk usage for specific file types:
    ```
    du -ch *.txt
    ```
    This shows the disk usage for all .txt files in the current directory and their total.

14. Find the largest directories:
    ```
    du -h /path/to/directory | sort -rh | head -n 5
    ```
    This lists the 5 largest directories or files.

Important Notes:
- `du` calculates actual disk usage, which may differ from the file size due to factors like file system block size.
- Root privileges may be required to access certain directories.
- For large directories, `du` can take a significant amount of time to complete.
- Combining `du` with other commands like `sort` and `head` can be very useful for finding large files or directories.
- The `-a` option can significantly increase the output, especially in directories with many files.
- Unlike `df`, `du` shows the space used by files and directories, not the free space on the file system.

