# Comprehensive Guide to the 'sed' Command

[Back to Linux Commands](../readme.md)

The 'sed' command in Unix and Linux systems is a stream editor used to perform basic text transformations on an input stream (a file or input from a pipeline). The name 'sed' stands for "stream editor".

## Basic Syntax

```
sed [OPTIONS] 'command' file(s)
sed [OPTIONS] -f scriptfile file(s)
```

## Common Options

1. `-n, --quiet, --silent`: 
   Suppress automatic printing of pattern space.

   Example:
   ```
   sed -n 'p' file.txt
   ```

2. `-e script, --expression=script`: 
   Add the script to the commands to be executed.

   Example:
   ```
   sed -e 's/foo/bar/' -e 's/baz/qux/' file.txt
   ```

3. `-f script-file, --file=script-file`: 
   Add the contents of script-file to the commands to be executed.

   Example:
   ```
   sed -f sedscript.txt file.txt
   ```

4. `-i[SUFFIX], --in-place[=SUFFIX]`: 
   Edit files in place (makes backup if SUFFIX supplied).

   Example:
   ```
   sed -i.bak 's/foo/bar/' file.txt
   ```

5. `-E, -r, --regexp-extended`: 
   Use extended regular expressions in the script.

   Example:
   ```
   sed -E 's/[0-9]+/NUMBER/' file.txt
   ```

## Additional Options

6. `-l N, --line-length=N`: 
   Specify the desired line-wrap length for the 'l' command.

7. `--posix`: 
   Disable all GNU extensions.

8. `-s, --separate`: 
   Consider files as separate rather than as a single continuous long stream.

9. `-u, --unbuffered`: 
   Load minimal amounts of data from the input files and flush the output buffers more often.

10. `--help`: 
    Display help information and exit.

11. `--version`: 
    Output version information and exit.

## Sed Commands

- `s/regexp/replacement/`: Substitute matches of regexp with replacement.
- `p`: Print the current pattern space.
- `d`: Delete the current pattern space and start the next cycle.
- `a\text`: Append text after a line.
- `i\text`: Insert text before a line.
- `c\text`: Change lines with text.
- `y/source/dest/`: Translate characters.
- `q`: Quit sed without processing any more input.
- `r filename`: Read file contents.
- `w filename`: Write pattern space to file.
- `!`: Apply command to lines not matching the address.

## Usage Examples

1. Basic substitution:
   ```
   sed 's/old/new/' file.txt
   ```

2. Global substitution (replace all occurrences):
   ```
   sed 's/old/new/g' file.txt
   ```

3. Print only lines matching a pattern:
   ```
   sed -n '/pattern/p' file.txt
   ```

4. Delete lines matching a pattern:
   ```
   sed '/pattern/d' file.txt
   ```

5. Replace on a specific line number:
   ```
   sed '3s/old/new/' file.txt
   ```

6. Replace between two line numbers:
   ```
   sed '2,5s/old/new/' file.txt
   ```

7. Append line after match:
   ```
   sed '/pattern/a\New line' file.txt
   ```

8. Insert line before match:
   ```
   sed '/pattern/i\New line' file.txt
   ```

9. Change whole line on match:
   ```
   sed '/pattern/c\New line' file.txt
   ```

10. Use capture groups:
    ```
    sed 's/\(foo\)bar/\1baz/' file.txt
    ```

11. Multiple commands:
    ```
    sed -e 's/foo/bar/' -e 's/baz/qux/' file.txt
    ```

12. Use extended regular expressions:
    ```
    sed -E 's/[0-9]+/NUMBER/' file.txt
    ```

13. Read commands from a file:
    ```
    sed -f commands.sed file.txt
    ```

14. In-place editing with backup:
    ```
    sed -i.bak 's/foo/bar/' file.txt
    ```

15. Print specific lines (e.g., lines 1-3):
    ```
    sed -n '1,3p' file.txt
    ```

16. Remove empty lines:
    ```
    sed '/^$/d' file.txt
    ```

17. Remove comments and empty lines:
    ```
    sed -e 's/#.*$//' -e '/^$/d' file.txt
    ```

18. Add line numbers:
    ```
    sed = file.txt | sed 'N;s/\n/\t/'
    ```

19. Use variables in sed:
    ```
    old="foo"; new="bar"; sed "s/$old/$new/g" file.txt
    ```

20. Transliterate characters:
    ```
    sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/' file.txt
    ```

Remember, sed is a powerful tool that can be used for complex text transformations. It's often used in shell scripts and in combination with other Unix/Linux commands. When used with the -i option, always be careful as it modifies files in-place. It's a good practice to make a backup before performing in-place edits.

[Back to Linux Commands](../readme.md)
