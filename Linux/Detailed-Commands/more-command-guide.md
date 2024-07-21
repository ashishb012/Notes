# more Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `more` command in Unix and Linux is a pager used to view text files one screen at a time. Its basic syntax is:

```
more [OPTIONS] FILE
```

## Common Options

1. `-d`: Display helpful prompts
2. `-f`: Count logical lines, not screen lines
3. `-l`: Suppress pause after form feed
4. `-c`: Do not scroll, display text and clean line by line
5. `-p`: Do not scroll, clean screen and display text
6. `-s`: Squeeze multiple blank lines into one
7. `-u`: Suppress underlining
8. `+/pattern`: Start displaying file at first line containing the pattern
9. `+num`: Start displaying file at line number num

## Interactive Commands

While viewing a file with `more`, you can use various commands:

- `Space` or `f`: Display next screen
- `Enter`: Display next line
- `b`: Go back one screen (not available on all systems)
- `/pattern`: Search forward for pattern
- `n`: Repeat previous search
- `=`: Display current line number
- `:f`: Display current file name and line number
- `q` or `Q`: Quit more
- `v`: Start up the editor specified by the VISUAL environment variable at the current line

## Examples

1. Basic usage:
   ```
   more filename.txt
   ```
   This opens `filename.txt` for viewing.

2. View with helpful prompts:
   ```
   more -d filename.txt
   ```
   This displays the file with additional prompts for navigation.

3. Squeeze multiple blank lines:
   ```
   more -s filename.txt
   ```
   This reduces multiple blank lines to a single blank line.

4. Start at a specific line:
   ```
   more +100 filename.txt
   ```
   This opens the file starting at line 100.

5. Start at the first occurrence of a pattern:
   ```
   more +/pattern filename.txt
   ```
   This opens the file at the first line containing "pattern".

6. View multiple files:
   ```
   more file1.txt file2.txt
   ```
   This allows viewing multiple files in sequence.

7. Use with pipes:
   ```
   ls -l | more
   ```
   This pipes the output of `ls -l` to `more` for viewing.

8. Display without scrolling, clearing the screen for each page:
   ```
   more -p filename.txt
   ```
   This clears the screen before displaying each page.

9. Count logical lines instead of screen lines:
   ```
   more -f filename.txt
   ```
   This is useful for files with very long lines.

10. Suppress underlining:
    ```
    more -u filename.txt
    ```
    This is useful when viewing files with underlining that may not display correctly.

Important Notes:
- `more` is simpler and less feature-rich compared to `less`.
- Unlike `less`, `more` generally only allows forward navigation through a file.
- The exact behavior and available options of `more` can vary between different Unix and Linux systems.
- On many modern systems, `more` is often symlinked to `less` for enhanced functionality.
- `more` is still widely available and can be useful in scripts or on systems where `less` is not installed.
- The `v` command to open an editor may not be available in all versions of `more`.


[Back to Linux Commands](../readme.md)
