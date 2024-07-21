# Comprehensive Guide to the 'chmod' Command

[Back to Linux Commands](../readme.md)

The 'chmod' command in Unix and Linux systems is used to change the access permissions of files and directories. The name 'chmod' stands for "change mode".

## Basic Syntax

```
chmod [OPTIONS] MODE FILE(s)
```

## Modes

Permissions can be specified in two ways:

1. Symbolic mode: using letters and symbols
2. Octal mode: using numbers

### Symbolic Mode

- u: user/owner
- g: group
- o: others
- a: all (equivalent to ugo)

- +: add permission
- -: remove permission
- =: set permission

- r: read
- w: write
- x: execute

### Octal Mode

- 4: read
- 2: write
- 1: execute

## Common Options

1. `-R, --recursive`: 
   Change permissions recursively, including subdirectories and their contents.

   Example:
   ```
   chmod -R 755 /home/user/directory
   ```

2. `-v, --verbose`: 
   Output a diagnostic for every file processed.

   Example:
   ```
   chmod -v u+x script.sh
   ```

3. `-c, --changes`: 
   Like verbose but report only when a change is made.

   Example:
   ```
   chmod -c g+w file.txt
   ```

4. `-f, --silent, --quiet`: 
   Suppress most error messages.

   Example:
   ```
   chmod -f 644 file.txt
   ```

5. `--preserve-root`: 
   Fail to operate recursively on '/'.

   Example:
   ```
   chmod --preserve-root -R 755 /
   ```

6. `--reference=RFILE`: 
   Use RFILE's mode instead of MODE values.

   Example:
   ```
   chmod --reference=ref_file.txt target_file.txt
   ```

## Additional Options

7. `--no-preserve-root`: 
    Do not treat '/' specially (the default).

8. `-H`: 
    If a command line argument is a symbolic link to a directory, traverse it.

9. `-L`: 
    Traverse every symbolic link to a directory encountered.

10. `-P`: 
    Do not traverse any symbolic links (default).

11. `--help`: 
    Display help information and exit.

12. `--version`: 
    Output version information and exit.

## Usage Examples

1. Give the owner execute permissions:
   ```
   chmod u+x script.sh
   ```

2. Remove write permissions for group and others:
   ```
   chmod go-w file.txt
   ```

3. Set read and write permissions for owner, and read-only for group and others:
   ```
   chmod u=rw,go=r file.txt
   ```

4. Use octal notation to set permissions (rwxr-xr-x):
   ```
   chmod 755 file.txt
   ```

5. Recursively change permissions of a directory:
   ```
   chmod -R u+rwX,go+rX,go-w /path/to/directory
   ```

6. Add execute permission for all (user, group, others):
   ```
   chmod a+x script.sh
   ```

7. Set the setuid bit (allows the file to be run with the permissions of the owner):
   ```
   chmod u+s executable_file
   ```

8. Set the sticky bit on a directory (only file owner can delete or rename files):
   ```
   chmod +t /shared_directory
   ```

9. Use reference file to set permissions:
   ```
   chmod --reference=ref_file.txt target_file.txt
   ```

10. Remove all permissions for group and others:
    ```
    chmod go= file.txt
    ```

11. Add read and execute permissions for user and group, but not others:
    ```
    chmod ug+rx,o-rx file.txt
    ```

12. Set full permissions (rwx) for owner, read and execute (r-x) for group and others:
    ```
    chmod 755 file.txt
    ```

13. Change permissions recursively with verbose output:
    ```
    chmod -Rv u=rwX,go=rX /path/to/directory
    ```

14. Set the setgid bit on a directory (new files inherit the directory's group):
    ```
    chmod g+s /shared_directory
    ```

15. Use symbolic mode to set exact permissions:
    ```
    chmod u=rwx,g=rx,o= file.txt
    ```

Remember that to use 'chmod', you typically need to be the owner of the file or have superuser (root) privileges. Always be cautious when changing permissions, especially when using the recursive option, as it can affect system functionality if used incorrectly.

[Back to Linux Commands](../readme.md)
