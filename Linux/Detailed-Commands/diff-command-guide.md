# Comprehensive Guide to the 'diff' Command

[Back to Linux Commands](../readme.md)

The 'diff' command in Unix and Linux systems is used to compare files line by line. It can also compare directories. The output shows the changes required to make the first file identical to the second file.

## Basic Syntax

```
diff [OPTIONS] FILE1 FILE2
```

## Common Options

1. `-u, --unified`:
   Output 3 lines of unified context.

   Example:
   ```
   diff -u file1.txt file2.txt
   ```

2. `-c, --context`:
   Output 3 lines of copied context.

   Example:
   ```
   diff -c file1.txt file2.txt
   ```

3. `-y, --side-by-side`:
   Output in two columns.

   Example:
   ```
   diff -y file1.txt file2.txt
   ```

4. `-i, --ignore-case`:
   Ignore case differences in file contents.

   Example:
   ```
   diff -i file1.txt file2.txt
   ```

5. `-b, --ignore-space-change`:
   Ignore changes in the amount of white space.

   Example:
   ```
   diff -b file1.txt file2.txt
   ```

6. `-w, --ignore-all-space`:
   Ignore all white space.

   Example:
   ```
   diff -w file1.txt file2.txt
   ```

7. `-B, --ignore-blank-lines`:
   Ignore changes where lines are all blank.

   Example:
   ```
   diff -B file1.txt file2.txt
   ```

8. `-r, --recursive`:
   Recursively compare any subdirectories found.

   Example:
   ```
   diff -r dir1 dir2
   ```

9. `-q, --brief`:
   Report only when files differ.

   Example:
   ```
   diff -q file1.txt file2.txt
   ```

10. `-s, --report-identical-files`:
    Report when two files are the same.

    Example:
    ```
    diff -s file1.txt file2.txt
    ```

## Additional Options

11. `--normal`:
    Output a normal diff (the default).

12. `-e, --ed`:
    Output an ed script.

13. `-n, --rcs`:
    Output an RCS format diff.

14. `--line-format=LFMT`:
    Format all input lines with LFMT.

15. `--LTYPE-line-format=LFMT`:
    Format LTYPE input lines with LFMT. LTYPE is 'old', 'new', or 'unchanged'.

16. `-p, --show-c-function`:
    Show which C function each change is in.

17. `-F, --show-function-line=RE`:
    Show the most recent line matching RE.

18. `--label LABEL`:
    Use LABEL instead of file name in output headers.

19. `-t, --expand-tabs`:
    Expand tabs to spaces in output.

20. `-T, --initial-tab`:
    Make tabs line up by prepending a tab.

21. `--tabsize=NUM`:
    Tab stops every NUM (default 8) print columns.

22. `--suppress-common-lines`:
    Do not output common lines (used with -y).

23. `-d, --minimal`:
    Try hard to find a smaller set of changes.

24. `--horizon-lines=NUM`:
    Keep NUM lines of the common prefix and suffix.

25. `--speed-large-files`:
    Assume large files and many scattered small changes.

## Usage Examples

1. Compare two files:
   ```
   diff file1.txt file2.txt
   ```

2. Compare two files, ignoring whitespace:
   ```
   diff -w file1.txt file2.txt
   ```

3. Compare two files in a side-by-side format:
   ```
   diff -y file1.txt file2.txt
   ```

4. Compare two files and show the differences in unified format:
   ```
   diff -u file1.txt file2.txt
   ```

5. Compare two directories recursively:
   ```
   diff -r dir1 dir2
   ```

6. Compare two files, ignoring case differences:
   ```
   diff -i file1.txt file2.txt
   ```

7. Compare two files, showing only whether they differ:
   ```
   diff -q file1.txt file2.txt
   ```

8. Compare two files, ignoring blank lines:
   ```
   diff -B file1.txt file2.txt
   ```

9. Compare two files, showing C function names:
   ```
   diff -p file1.c file2.c
   ```

10. Compare two files, with custom labels in the output:
    ```
    diff --label "Original" --label "Modified" file1.txt file2.txt
    ```

Remember that the 'diff' command is often used in combination with other commands or in scripts for tasks like creating patches or checking for changes in files. The output of 'diff' can be further processed or used as input for other tools.

[Back to Linux Commands](../readme.md)
