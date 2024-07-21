# tail Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `tail` command in Unix and Linux is used to output the last part of files. By default, it prints the last 10 lines of each file. Its basic syntax is:

```
tail [OPTIONS] [FILE]...
```

## Common Options

1. `-n NUM` or `--lines=NUM`: Print the last NUM lines instead of the last 10
2. `-c NUM` or `--bytes=NUM`: Print the last NUM bytes
3. `-f` or `--follow`: Output appended data as the file grows
4. `-F`: Same as -f, but keep retrying to open the file if it becomes inaccessible
5. `-q` or `--quiet`, `--silent`: Never print headers giving file names
6. `-v` or `--verbose`: Always print headers giving file names
7. `--pid=PID`: With -f, terminate after process ID, PID dies
8. `-s NUM` or `--sleep-interval=NUM`: With -f, sleep for approximately NUM seconds between iterations
9. `-z` or `--zero-terminated`: Line delimiter is NUL, not newline
10. `--help`: Display help information
11. `--version`: Output version information and exit

## Examples

1. Basic usage (display last 10 lines):
   ```
   tail filename.txt
   ```
   This displays the last 10 lines of `filename.txt`.

2. Display a specific number of lines:
   ```
   tail -n 5 filename.txt
   ```
   This shows the last 5 lines of the file.

3. Display a specific number of bytes:
   ```
   tail -c 100 filename.txt
   ```
   This outputs the last 100 bytes of the file.

4. Follow file changes in real-time:
   ```
   tail -f logfile.txt
   ```
   This continuously displays new lines added to `logfile.txt`.

5. Follow changes and retry if file becomes inaccessible:
   ```
   tail -F logfile.txt
   ```
   Similar to -f, but keeps trying to read the file if it becomes inaccessible.

6. Display lines from multiple files:
   ```
   tail file1.txt file2.txt
   ```
   This shows the last 10 lines of each file, with headers indicating the file names.

7. Suppress file headers:
   ```
   tail -q file1.txt file2.txt
   ```
   This displays the last 10 lines of each file without file name headers.

8. Always display file headers:
   ```
   tail -v filename.txt
   ```
   This ensures the file name is displayed as a header, even if only one file is processed.

9. Use with pipes:
   ```
   ls -l | tail -n 5
   ```
   This displays the last 5 lines of the `ls -l` command output.

10. Display all but the first N lines:
    ```
    tail -n +5 filename.txt
    ```
    This shows all lines starting from the 5th line of the file.

11. Follow a file and exit when a process ends:
    ```
    tail -f logfile.txt --pid=1234
    ```
    This follows `logfile.txt` and exits when process 1234 terminates.

12. Follow multiple files:
    ```
    tail -f file1.log file2.log
    ```
    This follows and displays new content from both files.

13. Use zero-terminated lines:
    ```
    tail -z -n 5 filename.txt
    ```
    This is useful for files with null-terminated lines, often used in programming contexts.

14. Specify sleep interval when following:
    ```
    tail -f -s 2 logfile.txt
    ```
    This follows `logfile.txt`, checking for new content every 2 seconds.

Important Notes:
- When no file is specified, `tail` reads from standard input.
- The `-f` option is particularly useful for monitoring log files in real-time.
- `tail` is often used in system administration and debugging to monitor the most recent entries in log files.
- The `-n +NUM` syntax allows you to output all lines starting with line NUM, which can be useful for skipping headers.
- `tail` is complementary to the `head` command, which displays the beginning of files.


[Back to Linux Commands](../readme.md)
