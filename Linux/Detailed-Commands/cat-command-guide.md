# cat Command Guide

[Back to Linux Commands](../readme.md)

## Basic Syntax

```
cat [OPTION]... [FILE]...
```

## Purpose

The `cat` command, short for "concatenate", is used to read data from files and output their contents. It can be used to display file contents, combine multiple files, and create new files.

## Common Options

1. `-A, --show-all`: Equivalent to -vET
2. `-b, --number-nonblank`: Number nonempty output lines, overrides -n
3. `-e`: Equivalent to -vE
4. `-E, --show-ends`: Display $ at end of each line
5. `-n, --number`: Number all output lines
6. `-s, --squeeze-blank`: Suppress repeated empty output lines
7. `-t`: Equivalent to -vT
8. `-T, --show-tabs`: Display TAB characters as ^I
9. `-u`: (ignored)
10. `-v, --show-nonprinting`: Use ^ and M- notation, except for LFD and TAB
11. `--help`: Display help information and exit
12. `--version`: Output version information and exit

## Examples

1. Display contents of a file:
   ```
   cat file.txt
   ```

2. Display contents of multiple files:
   ```
   cat file1.txt file2.txt
   ```

3. Create a new file and add text (press Ctrl+D to save and exit):
   ```
   cat > newfile.txt
   ```

4. Append text to an existing file:
   ```
   cat >> existingfile.txt
   ```

5. Display file contents with line numbers:
   ```
   cat -n file.txt
   ```

6. Display file contents with line numbers for non-blank lines:
   ```
   cat -b file.txt
   ```

7. Display file contents and show ends of lines:
   ```
   cat -E file.txt
   ```

8. Display file contents and show tabs:
   ```
   cat -T file.txt
   ```

9. Display file contents and squeeze blank lines:
   ```
   cat -s file.txt
   ```

10. Display all characters (including non-printing ones):
    ```
    cat -A file.txt
    ```

11. Combine multiple files into a single file:
    ```
    cat file1.txt file2.txt > combined.txt
    ```

12. Display contents of all .txt files in current directory:
    ```
    cat *.txt
    ```

13. Use cat with pipes to filter output:
    ```
    cat file.txt | grep "search_term"
    ```

14. Use cat to display file contents in reverse order (using tac):
    ```
    tac file.txt
    ```

15. Use cat to display contents of a binary file:
    ```
    cat -v binary_file
    ```

Remember to always consult the manual (`man cat`) or use `cat --help` for the most up-to-date and system-specific information, as options may vary slightly between different Unix-like systems.

[Back to Linux Commands](../readme.md)
