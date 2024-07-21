# gzip and gunzip Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `gzip` command is used to compress files, while `gunzip` is used to decompress files compressed by gzip. These commands are often used in Unix and Linux systems for efficient file storage and transfer.

## gzip Command

Basic syntax:
```
gzip [options] [filenames ...]
```

### Common gzip Options

1. `-c`, `--stdout`: Write output on standard output; keep original files unchanged
2. `-d`, `--decompress`: Decompress (same as gunzip)
3. `-f`, `--force`: Force overwrite of output file and compress links
4. `-k`, `--keep`: Keep (don't delete) input files during compression or decompression
5. `-l`, `--list`: List compressed file contents
6. `-n`, `--no-name`: Do not save or restore the original name and timestamp
7. `-N`, `--name`: Save or restore the original name and timestamp
8. `-q`, `--quiet`: Suppress all warnings
9. `-r`, `--recursive`: Operate recursively on directories
10. `-t`, `--test`: Test compressed file integrity
11. `-v`, `--verbose`: Verbose mode
12. `-#`, `--fast`, `--best`: Regulate the speed of compression using the specified digit #, where -1 or --fast indicates the fastest compression method (less compression) and -9 or --best indicates the slowest compression method (best compression). Default is -6.

### gzip Examples

1. Compress a single file:
   ```
   gzip file.txt
   ```
   This creates `file.txt.gz` and removes the original file.

2. Compress multiple files:
   ```
   gzip file1.txt file2.txt file3.txt
   ```

3. Compress and keep original files:
   ```
   gzip -k largefile.dat
   ```

4. Use maximum compression:
   ```
   gzip -9 hugefile.xml
   ```

5. Compress all files in a directory recursively:
   ```
   gzip -r ./mydirectory
   ```

6. View contents of a compressed file without decompressing:
   ```
   gzip -dc file.gz | less
   ```

7. Compress and output to stdout:
   ```
   gzip -c inputfile > outputfile.gz
   ```

8. Test the integrity of a compressed file:
   ```
   gzip -t file.gz
   ```

9. List information about a compressed file:
   ```
   gzip -l file.gz
   ```

10. Force compression even if a .gz file already exists:
    ```
    gzip -f alreadycompressed.gz
    ```

## gunzip Command

Basic syntax:
```
gunzip [options] [file ...]
```

### Common gunzip Options

Most of gunzip's options are the same as gzip. Here are some commonly used ones:

1. `-c`, `--stdout`: Write output on standard output; keep original files unchanged
2. `-f`, `--force`: Force overwrite of output file and compress links
3. `-k`, `--keep`: Keep (don't delete) input files during decompression
4. `-l`, `--list`: List compressed file contents
5. `-q`, `--quiet`: Suppress all warnings
6. `-r`, `--recursive`: Operate recursively on directories
7. `-t`, `--test`: Test compressed file integrity
8. `-v`, `--verbose`: Verbose mode

### gunzip Examples

1. Decompress a file:
   ```
   gunzip file.txt.gz
   ```
   This creates `file.txt` and removes the .gz file.

2. Decompress multiple files:
   ```
   gunzip file1.gz file2.gz file3.gz
   ```

3. Decompress and keep original compressed files:
   ```
   gunzip -k archive.tar.gz
   ```

4. Decompress to standard output:
   ```
   gunzip -c file.gz > newfile
   ```

5. Test integrity of a gzipped file:
   ```
   gunzip -t file.gz
   ```

6. Decompress all .gz files in a directory recursively:
   ```
   gunzip -r ./mydirectory
   ```

7. List contents of a compressed file without decompressing:
   ```
   gunzip -l file.gz
   ```

8. Force decompression even if the file doesn't have a .gz extension:
   ```
   gunzip -f compressedfile
   ```

Remember that `gzip` only compresses single files. To compress multiple files or directories into a single file, use `tar` with `gzip`, like this:
```
tar czvf archive.tar.gz directory/
```

And to extract:
```
tar xzvf archive.tar.gz
```

`gzip` and `gunzip` are often used in pipelines with other commands for efficient data processing and transfer in Unix-like systems.

[Back to Linux Commands](../readme.md)
