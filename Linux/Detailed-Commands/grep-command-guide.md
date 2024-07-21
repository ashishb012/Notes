# Comprehensive Guide to the 'grep' Command

[Back to Linux Commands](../readme.md)

The 'grep' command in Unix and Linux systems is used for searching and matching text patterns. The name 'grep' stands for "global regular expression print".

## Basic Syntax

```
grep [OPTIONS] PATTERN [FILE...]
```

## Common Options

1. `-i, --ignore-case`: 
   Ignore case distinctions in both the PATTERN and the input files.

   Example:
   ```
   grep -i "hello" file.txt
   ```

2. `-v, --invert-match`: 
   Invert the sense of matching, to select non-matching lines.

   Example:
   ```
   grep -v "error" logfile.txt
   ```

3. `-w, --word-regexp`: 
   Select only those lines containing matches that form whole words.

   Example:
   ```
   grep -w "is" file.txt
   ```

4. `-n, --line-number`: 
   Prefix each line of output with the line number within its input file.

   Example:
   ```
   grep -n "pattern" file.txt
   ```

5. `-r, -R, --recursive`: 
   Read all files under each directory, recursively.

   Example:
   ```
   grep -r "TODO" /path/to/project
   ```

6. `-l, --files-with-matches`: 
   Print only names of FILEs containing matches.

   Example:
   ```
   grep -l "error" *.log
   ```

7. `-c, --count`: 
   Print only a count of matching lines per FILE.

   Example:
   ```
   grep -c "warning" logfile.txt
   ```

8. `-e PATTERN, --regexp=PATTERN`: 
   Use PATTERN as the pattern. Useful for specifying multiple search patterns.

   Example:
   ```
   grep -e "error" -e "warning" logfile.txt
   ```

9. `-f FILE, --file=FILE`: 
   Obtain patterns from FILE, one per line.

   Example:
   ```
   grep -f patterns.txt file.txt
   ```

10. `-E, --extended-regexp`: 
    Interpret PATTERN as an extended regular expression.

    Example:
    ```
    grep -E "apple|orange" fruits.txt
    ```

## Additional Options

11. `-o, --only-matching`: 
    Print only the matched parts of a matching line.

12. `-q, --quiet, --silent`: 
    Quiet mode; suppress normal output. Useful in shell scripts.

13. `-s, --no-messages`: 
    Suppress error messages about nonexistent or unreadable files.

14. `-b, --byte-offset`: 
    Print the byte offset with output lines.

15. `-H, --with-filename`: 
    Print the file name for each match.

16. `-h, --no-filename`: 
    Suppress the prefixing of file names on output.

17. `-m NUM, --max-count=NUM`: 
    Stop reading a file after NUM matching lines.

18. `-A NUM, --after-context=NUM`: 
    Print NUM lines of trailing context after matching lines.

19. `-B NUM, --before-context=NUM`: 
    Print NUM lines of leading context before matching lines.

20. `-C NUM, --context=NUM`: 
    Print NUM lines of output context.

## Usage Examples

1. Search for a string in a file:
   ```
   grep "hello" file.txt
   ```

2. Case-insensitive search:
   ```
   grep -i "HELLO" file.txt
   ```

3. Search for whole words only:
   ```
   grep -w "is" file.txt
   ```

4. Search and display line numbers:
   ```
   grep -n "error" logfile.txt
   ```

5. Search recursively in a directory:
   ```
   grep -r "TODO" /path/to/project
   ```

6. Search for multiple patterns:
   ```
   grep -e "error" -e "warning" logfile.txt
   ```

7. Invert the match (show lines that don't match):
   ```
   grep -v "success" logfile.txt
   ```

8. Count the number of matches:
   ```
   grep -c "error" logfile.txt
   ```

9. Show only the part of the line that matched:
   ```
   grep -o "IP address: [0-9.]*" server.log
   ```

10. Search for a pattern and show surrounding context:
    ```
    grep -C 3 "error" logfile.txt
    ```

11. Use regular expressions:
    ```
    grep -E "^[A-Z]{3}-[0-9]{4}$" codes.txt
    ```

12. Search for files containing a pattern:
    ```
    grep -l "TODO" *.py
    ```

13. Search for a pattern and stop after 5 matches:
    ```
    grep -m 5 "warning" large_logfile.txt
    ```

14. Use 'or' logic with grep:
    ```
    grep "apple\|orange" fruits.txt
    ```

15. Search for a pattern in gzipped files:
    ```
    zgrep "error" *.gz
    ```

Remember that grep is a powerful tool, especially when combined with regular expressions. It's widely used in scripts and command-line operations for text processing and log analysis. Always be cautious when using grep with sudo or on system files to avoid unintended consequences.

[Back to Linux Commands](../readme.md)
