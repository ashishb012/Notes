# Comprehensive Guide to the 'tr' Command

[Back to Linux Commands](../readme.md)

The 'tr' (translate) command in Unix and Linux is used to translate or delete characters. It can be used to perform various character-based operations like case conversion, basic character replacement, and removing specific characters from the input.

## Basic Syntax

```
tr [OPTION]... SET1 [SET2]
```

## Common Options

1. `-d, --delete`: 
   Delete characters in SET1, do not translate.

   Example:
   ```
   echo "hello world" | tr -d 'aeiou'
   ```

2. `-s, --squeeze-repeats`: 
   Replace each sequence of a repeated character that is listed in the last specified SET, with a single occurrence of that character.

   Example:
   ```
   echo "hello    world" | tr -s ' '
   ```

3. `-c, --complement`: 
   Use the complement of SET1.

   Example:
   ```
   echo "hello 123 world" | tr -cd '[:digit:]'
   ```

4. `-t, --truncate-set1`: 
   First truncate SET1 to length of SET2.

   Example:
   ```
   echo "hello" | tr -t 'el' 'EL'
   ```

## Additional Options

5. `--help`: 
   Display help information and exit.

6. `--version`: 
   Output version information and exit.

## Character Sets and Classes

- `[:alnum:]`: All letters and digits
- `[:alpha:]`: All letters
- `[:blank:]`: All horizontal whitespace
- `[:cntrl:]`: All control characters
- `[:digit:]`: All digits
- `[:graph:]`: All printable characters, not including space
- `[:lower:]`: All lowercase letters
- `[:print:]`: All printable characters, including space
- `[:punct:]`: All punctuation characters
- `[:space:]`: All horizontal or vertical whitespace
- `[:upper:]`: All uppercase letters
- `[:xdigit:]`: All hexadecimal digits

## Usage Examples

1. Convert lowercase to uppercase:
   ```
   echo "hello world" | tr 'a-z' 'A-Z'
   ```

2. Delete all occurrences of a specific character:
   ```
   echo "hello world" | tr -d 'l'
   ```

3. Translate spaces to tabs:
   ```
   echo "hello world" | tr ' ' '\t'
   ```

4. Remove all non-printable characters:
   ```
   tr -cd '[:print:]' < file.txt
   ```

5. Squeeze repeating characters:
   ```
   echo "hello      world" | tr -s ' '
   ```

6. Remove all characters except digits:
   ```
   echo "hello 123 world 456" | tr -cd '[:digit:]'
   ```

7. Replace multiple characters:
   ```
   echo "hello world" | tr 'aeiou' '12345'
   ```

8. Convert Windows/DOS text file to Unix format:
   ```
   tr -d '\r' < windowsfile.txt > unixfile.txt
   ```

9. Create a rot13 encoder/decoder:
   ```
   echo "hello world" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
   ```

10. Remove all whitespace:
    ```
    echo "hello   world  " | tr -d '[:space:]'
    ```

11. Complement option to keep only alphabetic characters:
    ```
    echo "hello world 123" | tr -cd '[:alpha:]'
    ```

12. Translate lowercase vowels to uppercase:
    ```
    echo "hello world" | tr 'aeiou' 'AEIOU'
    ```

13. Replace colons with newlines:
    ```
    echo "field1:field2:field3" | tr ':' '\n'
    ```

14. Remove backspace characters:
    ```
    tr -d '\b' < file.txt
    ```

15. Convert multiple spaces to a single comma:
    ```
    echo "hello   world   example" | tr -s ' ' ','
    ```

Remember that 'tr' operates on a character-by-character basis and is particularly useful for simple text transformations. It's often used in shell scripts and command pipelines for text processing tasks. For more complex pattern matching and replacement, tools like 'sed' or 'awk' are typically used.

[Back to Linux Commands](../readme.md)
