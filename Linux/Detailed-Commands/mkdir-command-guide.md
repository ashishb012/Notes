# mkdir Command Guide

[Back to Linux Commands](../readme.md)

The `mkdir` command is used to create directories (folders) in Unix and Unix-like operating systems. It can create multiple directories at once and also create parent directories as needed.

## Basic Syntax

```
mkdir [OPTION]... DIRECTORY...
```



## Common Options

1. `-p, --parents`: Create parent directories as needed, no error if existing
2. `-m, --mode=MODE`: Set file mode (as in chmod), not a=rwx - umask
3. `-v, --verbose`: Print a message for each created directory
4. `-Z`: Set SELinux security context of each created directory to the default type
5. `--context[=CTX]`: Like -Z, or if CTX is specified then set the SELinux or SMACK security context to CTX
6. `--help`: Display help information and exit
7. `--version`: Output version information and exit

## Examples

1. Create a single directory:
   ```
   mkdir new_directory
   ```

2. Create multiple directories:
   ```
   mkdir dir1 dir2 dir3
   ```

3. Create parent directories as needed:
   ```
   mkdir -p parent/child/grandchild
   ```

4. Create a directory and set permissions:
   ```
   mkdir -m 755 my_directory
   ```

5. Create a directory and display a message:
   ```
   mkdir -v verbose_directory
   ```

6. Create a directory with a space in the name:
   ```
   mkdir "My Documents"
   ```

7. Create multiple nested directories:
   ```
   mkdir -p project/{src,docs,tests}
   ```

8. Create a directory and set SELinux context (if supported):
   ```
   mkdir -Z selinux_directory
   ```

9. Create a directory with a specific date:
   ```
   mkdir $(date +%Y-%m-%d)
   ```

10. Create a directory and change into it immediately:
    ```
    mkdir new_dir && cd new_dir
    ```

11. Create directories with numbered names:
    ```
    mkdir dir{1..5}
    ```

12. Create a directory with specific owner and group (requires sudo):
    ```
    sudo mkdir -m 775 -p /var/www/mysite && sudo chown www-data:developers /var/www/mysite
    ```

13. Create a directory and set permissions for owner, group, and others separately:
    ```
    mkdir -m u=rwx,g=rx,o= my_private_dir
    ```

14. Create a directory and display help information:
    ```
    mkdir --help
    ```

15. Display mkdir version:
    ```
    mkdir --version
    ```

Remember to always consult the manual (`man mkdir`) or use `mkdir --help` for the most up-to-date and system-specific information, as options may vary slightly between different Unix-like systems.

[Back to Linux Commands](../readme.md)
