# ln Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `ln` command in Linux is used to create links between files. It can create both hard links and symbolic (soft) links. The basic syntax is:

```
ln [OPTIONS] TARGET LINK_NAME
```

## Common Options

1. `-s` or `--symbolic`: Create a symbolic link instead of a hard link
2. `-f` or `--force`: Remove existing destination files
3. `-i` or `--interactive`: Prompt whether to remove destinations
4. `-n` or `--no-dereference`: Treat LINK_NAME as a normal file if it is a symbolic link to a directory
5. `-v` or `--verbose`: Print name of each linked file
6. `-t DIRECTORY` or `--target-directory=DIRECTORY`: Specify the DIRECTORY in which to create the links
7. `-T` or `--no-target-directory`: Treat LINK_NAME as a normal file always
8. `-r` or `--relative`: Create symbolic links relative to link location

## Examples

1. Create a hard link:
   ```
   ln original.txt hard_link.txt
   ```
   This creates a hard link named `hard_link.txt` pointing to `original.txt`.

2. Create a symbolic link:
   ```
   ln -s original.txt symlink.txt
   ```
   This creates a symbolic link named `symlink.txt` pointing to `original.txt`.

3. Force creation of a link:
   ```
   ln -f existing_file.txt new_link.txt
   ```
   This creates a link, overwriting `new_link.txt` if it already exists.

4. Create a link with interactive prompt:
   ```
   ln -i original.txt interactive_link.txt
   ```
   This prompts for confirmation if `interactive_link.txt` already exists.

5. Create a symbolic link with verbose output:
   ```
   ln -sv /path/to/original.txt verbose_link.txt
   ```
   This creates a symbolic link and prints information about the operation.

6. Create multiple links in a specific directory:
   ```
   ln -t /path/to/linkdir file1.txt file2.txt file3.txt
   ```
   This creates links to `file1.txt`, `file2.txt`, and `file3.txt` in the specified directory.

7. Create a relative symbolic link:
   ```
   ln -sr /path/to/original.txt relative_link.txt
   ```
   This creates a symbolic link with a relative path, which can be useful when moving directories.

8. Create a symbolic link to a directory:
   ```
   ln -s /path/to/original_dir link_to_dir
   ```
   This creates a symbolic link to a directory.

9. Create a hard link for a directory (note: this is typically not allowed on most systems):
   ```
   ln /path/to/original_dir hard_link_to_dir
   ```
   This will usually fail, as hard links to directories are generally not permitted.

10. Create a symbolic link without dereferencing:
    ```
    ln -sn existing_symlink.txt no_dereference_link.txt
    ```
    This creates a symbolic link to `existing_symlink.txt` rather than its target.

Important Notes:
- Hard links can only be created for files, not directories.
- Hard links cannot span file systems.
- Symbolic links can point to directories and can span file systems.
- When a hard link is deleted, it doesn't affect the original file or other hard links.
- When the original file of a symbolic link is deleted, the symbolic link becomes a "dangling" link.
- Use symbolic links (`ln -s`) for most general-purpose linking needs.


[Back to Linux Commands](../readme.md)
