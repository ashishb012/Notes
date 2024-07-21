# Comprehensive Guide to the 'cmp' Command

[Back to Linux Commands](../readme.md)

The 'cmp' command in Unix and Linux systems is used to compare two files byte by byte. It's particularly useful for comparing binary files or when you need to know the exact position of the first difference between two files.

## Basic Syntax

```
cmp [OPTIONS] FILE1 FILE2 [SKIP1 [SKIP2]]
```

SKIP1 and SKIP2 are optional offsets (in bytes) to start comparison from in FILE1 and FILE2 respectively.

## Options

1. `-b, --print-bytes`:
   Print differing bytes.

   Example:
   ```
   cmp -b file1.txt file2.txt
   ```

2. `-i SKIP, --ignore-initial=SKIP`:
   Skip first SKIP bytes of both inputs.

   Example:
   ```
   cmp -i 10 file1.txt file2.txt
   ```

3. `-i SKIP1:SKIP2`:
   Skip first SKIP1 bytes of FILE1 and first SKIP2 bytes of FILE2.

   Example:
   ```
   cmp -i 10:20 file1.txt file2.txt
   ```

4. `-l, --verbose`:
   Output byte numbers and differing byte values.

   Example:
   ```
   cmp -l file1.txt file2.txt
   ```

5. `-n LIMIT, --bytes=LIMIT`:
   Compare at most LIMIT bytes.

   Example:
   ```
   cmp -n 100 file1.txt file2.txt
   ```

6. `-s, --quiet, --silent`:
   Output nothing; yield exit status only.

   Example:
   ```
   cmp -s file1.txt file2.txt
   ```

7. `--help`:
   Display help information and exit.

8. `-v, --version`:
   Output version information and exit.

## Usage Examples

1. Basic comparison of two files:
   ```
   cmp file1.txt file2.txt
   ```
   Output (if files differ):
   ```
   file1.txt file2.txt differ: char 20, line 2
   ```

2. Silent comparison (useful in scripts):
   ```
   cmp -s file1.txt file2.txt
   echo $?  # Print exit status
   ```
   Output:
   ```
   0  # if files are identical
   1  # if files differ
   2  # if an error occurred
   ```

3. Print differing bytes:
   ```
   cmp -b file1.txt file2.txt
   ```
   Output:
   ```
   file1.txt file2.txt differ: byte 20, line 2 is 141 A 142 B
   ```

4. Verbose output of all differing bytes:
   ```
   cmp -l file1.txt file2.txt
   ```
   Output:
   ```
   20 141 142
   21 142 143
   ```

5. Compare only first 50 bytes:
   ```
   cmp -n 50 file1.txt file2.txt
   ```

6. Skip first 10 bytes in both files:
   ```
   cmp -i 10 file1.txt file2.txt
   ```

7. Skip different number of bytes in each file:
   ```
   cmp -i 10:20 file1.txt file2.txt
   ```

8. Compare binary files:
   ```
   cmp binary1 binary2
   ```

9. Use in a shell script condition:
   ```bash
   if cmp -s file1.txt file2.txt
   then
       echo "Files are identical"
   else
       echo "Files differ"
   fi
   ```

10. Compare specific byte ranges:
    ```
    cmp file1.txt file2.txt 100 200
    ```
    This compares bytes 100-end of file1.txt with bytes 200-end of file2.txt.

## Key Points

- 'cmp' is particularly useful for binary files or when you need the exact position of differences.
- Unlike 'diff', 'cmp' stops at the first difference it finds by default.
- The '-s' option is useful in scripts where you only need to know if files are identical or not.
- 'cmp' can be used to compare parts of files using byte offsets.
- The exit status of 'cmp' can be used in shell scripts for conditional operations.

Remember that 'cmp' compares files byte by byte, so it's sensitive to all differences, including whitespace and line endings. For text file comparisons where you want to ignore certain types of differences, 'diff' might be more appropriate.

[Back to Linux Commands](../readme.md)
