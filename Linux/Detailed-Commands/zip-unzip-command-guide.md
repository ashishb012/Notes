# zip and unzip Command Guide: Options and Examples

The `zip` and `unzip` commands are used to package and compress (archive) files, and to extract files from archives.

## zip Command

Basic syntax:
```
zip [options] zipfile files_or_directories
```

### Common zip Options

1. `-r`: Recursively include files in directories
2. `-u`: Update existing entries if newer on the file system
3. `-m`: Move files into the archive (delete original files)
4. `-e`: Encrypt the archive with a password
5. `-j`: Junk (don't record) directory names
6. `-q`: Quiet mode (suppress informational messages)
7. `-v`: Verbose mode (show more information)
8. `-9`: Use maximum compression
9. `-0`: Store files without compression
10. `-x files`: Exclude specified files
11. `-i files`: Include only specified files
12. `-d`: Remove entries from the archive

### zip Examples

1. Create a simple zip archive:
   ```
   zip archive.zip file1 file2 file3
   ```

2. Create a zip archive including all files in a directory:
   ```
   zip -r archive.zip directory/
   ```

3. Update existing zip archive with newer files:
   ```
   zip -u archive.zip newfile
   ```

4. Create an encrypted zip archive:
   ```
   zip -e secure_archive.zip sensitive_file
   ```

5. Create a zip archive with maximum compression:
   ```
   zip -9 -r compressed_archive.zip large_directory/
   ```

6. Add files to an existing archive:
   ```
   zip -r existing_archive.zip new_file new_directory/
   ```

7. Exclude certain files while creating an archive:
   ```
   zip -r archive.zip directory/ -x "*.log"
   ```

8. Create a zip archive without compressing the files:
   ```
   zip -0 archive.zip large_file
   ```

9. Delete a file from an existing zip archive:
   ```
   zip -d archive.zip file_to_remove
   ```

10. Create a split zip archive (useful for large archives):
    ```
    zip -r -s 1g large_archive.zip large_directory/
    ```
    This creates 1GB split files.

## unzip Command

Basic syntax:
```
unzip [options] zipfile [file(s) to extract] [-d exdir]
```

### Common unzip Options

1. `-l`: List the contents of the archive without extracting
2. `-p`: Extract files to pipe (stdout)
3. `-t`: Test archive integrity
4. `-q`: Quiet mode
5. `-v`: Verbose mode
6. `-o`: Overwrite files without prompting
7. `-n`: Never overwrite existing files
8. `-d exdir`: Extract files into exdir
9. `-x files`: Exclude specified files
10. `-P password`: Use password for decryption

### unzip Examples

1. Extract all files from an archive:
   ```
   unzip archive.zip
   ```

2. List contents of a zip archive without extracting:
   ```
   unzip -l archive.zip
   ```

3. Extract files to a specific directory:
   ```
   unzip archive.zip -d /path/to/extract/to
   ```

4. Test the integrity of a zip archive:
   ```
   unzip -t archive.zip
   ```

5. Extract a single file from an archive:
   ```
   unzip archive.zip file_to_extract
   ```

6. Extract files while overwriting existing ones without prompting:
   ```
   unzip -o archive.zip
   ```

7. Extract an encrypted zip archive:
   ```
   unzip -P password secure_archive.zip
   ```

8. Extract files excluding certain files:
   ```
   unzip archive.zip -x "*.log"
   ```

9. Extract files without recreating the directory structure:
   ```
   unzip -j archive.zip
   ```

10. View the contents of a file in a zip archive without extracting:
    ```
    unzip -p archive.zip file_to_view
    ```

Remember that `zip` and `unzip` are widely used for cross-platform file compression and archiving. They maintain file attributes and can handle large files and directories. However, they don't offer as high compression ratios as some other formats like 7z or xz.

When working with sensitive data, always use encryption (`-e` option in zip) to protect your archives, especially when transmitting over networks or storing in unsecured locations.
