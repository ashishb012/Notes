# less Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `less` command in Linux is a powerful pager that allows you to view and navigate through text files. Its basic syntax is:

```
less [OPTIONS] FILE
```

## Common Options

1. `-N`: Show line numbers
2. `-i`: Ignore case in searches
3. `-X`: Leave file contents on screen when less exits
4. `-F`: Quit if entire file can be displayed on first screen
5. `-R`: Output "raw" control characters
6. `-S`: Chop long lines instead of wrapping
7. `-m`: Show more detailed prompt, including file position
8. `+F`: Keep reading file, stopping only when interrupted (like `tail -f`)
9. `-g`: Highlight only the last match for searches
10. `+/pattern`: Start at the first occurrence of "pattern" in the file

## Interactive Commands

While viewing a file with `less`, you can use various commands:

- `/pattern`: Search forward for "pattern"
- `?pattern`: Search backward for "pattern"
- `n`: Repeat previous search (forward)
- `N`: Repeat previous search (backward)
- `g`: Go to the first line of the file
- `G`: Go to the last line of the file
- `q`: Quit less
- `h`: Display help screen
- `spacebar`: Move forward one screen
- `b`: Move backward one screen
- `j` or `↓`: Move forward one line
- `k` or `↑`: Move backward one line
- `F`: Keep reading file, stopping only when interrupted (like `tail -f`)
- `=`: Show file information
- `v`: Open the current file in the default editor

## Examples

1. Basic usage:
   ```
   less filename.txt
   ```
   This opens `filename.txt` for viewing.

2. View with line numbers:
   ```
   less -N filename.txt
   ```
   This displays the file with line numbers on the left.

3. Case-insensitive search:
   ```
   less -i filename.txt
   ```
   This allows case-insensitive searching within the file.

4. View multiple files:
   ```
   less file1.txt file2.txt
   ```
   This opens multiple files. Use `:n` and `:p` to navigate between files.

5. Start at a specific line:
   ```
   less +100 filename.txt
   ```
   This opens the file at line 100.

6. Start at the first occurrence of a pattern:
   ```
   less +/pattern filename.txt
   ```
   This opens the file at the first occurrence of "pattern".

7. Follow file changes (like tail -f):
   ```
   less +F logfile.txt
   ```
   This follows the file, displaying new content as it's added.

8. Highlight search results:
   ```
   less -g filename.txt
   ```
   This highlights only the last match when searching.

9. View raw control characters:
   ```
   less -R colorful_output.txt
   ```
   This is useful for viewing files with color codes or other control characters.

10. Chop long lines:
    ```
    less -S wide_file.txt
    ```
    This chops long lines instead of wrapping them.

11. Use with pipes:
    ```
    command | less
    ```
    This pipes the output of a command to less for viewing.

12. Show more information in prompt:
    ```
    less -m filename.txt
    ```
    This shows a more detailed prompt, including the file position.

Important Notes:
- `less` is more feature-rich than `more` and allows backward movement in the file.
- You can customize `less` behavior by setting environment variables or creating a `.lesskey` file.
- `less` doesn't read the entire file at once, making it faster than some text editors for large files.
- The `v` command in `less` opens the file in the default editor (usually set by the VISUAL or EDITOR environment variable).
- `less` is particularly useful for viewing large log files or the output of long-running commands.


[Back to Linux Commands](../readme.md)
