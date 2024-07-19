# head Command Guide: Options and Examples

The `head` command in Unix and Linux is used to output the first part of files. By default, it prints the first 10 lines of each file. Its basic syntax is:

```
head [OPTIONS] [FILE]...
```

## Common Options

1. `-n NUM` or `--lines=NUM`: Print the first NUM lines instead of the first 10
2. `-c NUM` or `--bytes=NUM`: Print the first NUM bytes
3. `-q` or `--quiet`, `--silent`: Never print headers giving file names
4. `-v` or `--verbose`: Always print headers giving file names
5. `-z` or `--zero-terminated`: Line delimiter is NUL, not newline
6. `--help`: Display help information
7. `--version`: Output version information and exit

## Examples

1. Basic usage (display first 10 lines):
   ```
   head filename.txt
   ```
   This displays the first 10 lines of `filename.txt`.

2. Display a specific number of lines:
   ```
   head -n 5 filename.txt
   ```
   This shows the first 5 lines of the file.

3. Display a specific number of bytes:
   ```
   head -c 100 filename.txt
   ```
   This outputs the first 100 bytes of the file.

4. Display lines from multiple files:
   ```
   head file1.txt file2.txt
   ```
   This shows the first 10 lines of each file, with headers indicating the file names.

5. Suppress file headers:
   ```
   head -q file1.txt file2.txt
   ```
   This displays the first 10 lines of each file without file name headers.

6. Always display file headers:
   ```
   head -v filename.txt
   ```
   This ensures the file name is displayed as a header, even if only one file is processed.

7. Use with pipes:
   ```
   ls -l | head -n 5
   ```
   This displays the first 5 lines of the `ls -l` command output.

8. Display all but the last N lines:
   ```
   head -n -5 filename.txt
   ```
   This shows all lines except the last 5 of the file.

9. Use with wildcards:
   ```
   head -n 1 *.txt
   ```
   This displays the first line of all .txt files in the current directory.

10. Combine with other commands:
    ```
    ps aux | head -n 5
    ```
    This shows the first 5 lines of the process status, typically including the header and the 4 most resource-intensive processes.

11. Use zero-terminated lines:
    ```
    head -z -n 5 filename.txt
    ```
    This is useful for files with null-terminated lines, often used in programming contexts.

12. Display a specific number of characters:
    ```
    head -c 50 filename.txt
    ```
    This outputs the first 50 characters of the file.

Important Notes:
- When no file is specified, `head` reads from standard input.
- The `-n` and `-c` options are mutually exclusive; the last one specified determines the behavior.
- `head` is often used in scripts or in combination with other commands to process or analyze the beginning of files or command outputs.
- When using negative numbers with `-n`, it displays all but the last N lines, which can be useful for excluding footers or summary lines.
- `head` is complementary to the `tail` command, which displays the end of files.

