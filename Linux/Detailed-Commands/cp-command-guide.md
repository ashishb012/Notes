# cp Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `cp` (copy) command in Linux is used to copy files and directories. Its basic syntax is:

```
cp [OPTIONS] SOURCE DESTINATION
```

## Common Options

1. `-r` or `-R` or `--recursive`: Copy directories recursively
2. `-i` or `--interactive`: Prompt before overwrite
3. `-f` or `--force`: Force copy by removing the destination file if needed
4. `-n` or `--no-clobber`: Do not overwrite an existing file
5. `-u` or `--update`: Copy only when the SOURCE file is newer than the destination file or when the destination file is missing
6. `-v` or `--verbose`: Explain what is being done
7. `-p`: Preserve the specified attributes (default: mode,ownership,timestamps)
8. `-a` or `--archive`: Same as -dR --preserve=all
9. `-b` or `--backup`: Make a backup of each existing destination file
10. `-l` or `--link`: Hard link files instead of copying
11. `-s` or `--symbolic-link`: Make symbolic links instead of copying

## Examples

1. Basic copy operation:
   ```
   cp file1.txt /home/user/Documents/
   ```
   This copies `file1.txt` to the Documents directory.

2. Copy and rename:
   ```
   cp original.txt copy.txt
   ```
   This creates a copy of `original.txt` named `copy.txt`.

3. Copy multiple files:
   ```
   cp file1.txt file2.txt file3.txt /home/user/Documents/
   ```
   This copies all three files to the Documents directory.

4. Recursive copy (for directories):
   ```
   cp -r /home/user/SourceFolder /home/user/DestFolder
   ```
   This copies the entire SourceFolder and its contents to DestFolder.

5. Copy with interactive prompt:
   ```
   cp -i important_file.txt /home/user/Documents/
   ```
   This will prompt for confirmation if `important_file.txt` already exists in the destination.

6. Copy and preserve attributes:
   ```
   cp -p original.txt copy.txt
   ```
   This creates a copy preserving mode, ownership, and timestamp.

7. Copy only newer files:
   ```
   cp -u *.txt /home/user/Documents/
   ```
   This copies all `.txt` files, but only if they're newer than the versions in Documents.

8. Verbose copy:
   ```
   cp -v file.txt /home/user/Documents/
   ```
   This will show what the command is doing.

9. Create a backup of existing files:
   ```
   cp -b existing_file.txt /home/user/Documents/
   ```
   If `existing_file.txt` exists in Documents, it will be backed up before copying.

10. Create a hard link instead of copying:
    ```
    cp -l original.txt hardlink.txt
    ```
    This creates a hard link named `hardlink.txt` pointing to `original.txt`.

11. Create a symbolic link instead of copying:
    ```
    cp -s /path/to/original.txt symlink.txt
    ```
    This creates a symbolic link named `symlink.txt` pointing to `/path/to/original.txt`.

12. Archive copy:
    ```
    cp -a /source/directory /destination/
    ```
    This recursively copies the directory while preserving all file attributes and symlinks.

Remember to use `cp` carefully, especially with the `-f` option or when dealing with important data, as it can overwrite existing files.

[Back to Linux Commands](../readme.md)
