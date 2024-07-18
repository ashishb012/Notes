# mv Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `mv` (move) command in Linux is used to move or rename files and directories. Its basic syntax is:

```
mv [OPTIONS] SOURCE DESTINATION
```

## Common Options

1. `-i` or `--interactive`: Prompt before overwriting
2. `-f` or `--force`: Do not prompt before overwriting
3. `-n` or `--no-clobber`: Do not overwrite an existing file
4. `-u` or `--update`: Move only when the SOURCE file is newer than the destination file or when the destination file is missing
5. `-v` or `--verbose`: Explain what is being done
6. `-b` or `--backup`: Make a backup of each existing destination file
7. `-t DIRECTORY` or `--target-directory=DIRECTORY`: Move all SOURCE arguments into DIRECTORY

## Examples

1. Basic move operation:
   ```
   mv file1.txt /home/user/Documents/
   ```
   This moves `file1.txt` to the Documents directory.

2. Rename a file:
   ```
   mv oldname.txt newname.txt
   ```
   This renames `oldname.txt` to `newname.txt`.

3. Move multiple files:
   ```
   mv file1.txt file2.txt file3.txt /home/user/Documents/
   ```
   This moves all three files to the Documents directory.

4. Move with interactive prompt:
   ```
   mv -i important_file.txt /home/user/Documents/
   ```
   This will prompt for confirmation if `important_file.txt` already exists in the destination.

5. Move and create backup:
   ```
   mv -b file.txt /home/user/Documents/
   ```
   If `file.txt` exists in Documents, it will be backed up before moving.

6. Move only newer files:
   ```
   mv -u *.txt /home/user/Documents/
   ```
   This moves all `.txt` files, but only if they're newer than the versions in Documents.

7. Move files to a directory using the target option:
   ```
   mv -t /home/user/Documents/ file1.txt file2.txt file3.txt
   ```
   This is equivalent to the third example but uses the `-t` option.

8. Verbose move:
   ```
   mv -v file.txt /home/user/Documents/
   ```
   This will show what the command is doing.

9. Move directory:
   ```
   mv /home/user/OldFolder /home/user/NewFolder
   ```
   This moves the entire OldFolder to NewFolder. If NewFolder doesn't exist, OldFolder will be renamed to NewFolder.

10. Move and force overwrite:
    ```
    mv -f source_file.txt destination_file.txt
    ```
    This will overwrite `destination_file.txt` without prompting.

Remember to use `mv` carefully, especially with wildcards or the `-f` option, as it can lead to data loss if used incorrectly.

[Back to Linux Commands](../readme.md)
