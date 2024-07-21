# The `ftp` Command

[Back to Linux Commands](../readme.md)

The `ftp` command is used to transfer files to and from a remote network site using the File Transfer Protocol (FTP). It provides an interactive interface for connecting to FTP servers, navigating directories, and transferring files.

## Basic Syntax

```
ftp [options] [host [port]]
```

## Common Command-Line Options

1. `-i`: Turn off interactive prompting during multiple file transfers
2. `-n`: Suppress auto-login upon initial connection
3. `-v`: Verbose mode, displays FTP protocol messages
4. `-d`: Enable debugging mode
5. `-g`: Disable filename globbing (wildcard expansion)

## Common FTP Commands (once connected)

1. `open hostname`: Open connection to a new host
2. `user username`: Specify the user name
3. `cd directory`: Change remote directory
4. `lcd directory`: Change local directory
5. `pwd`: Print working directory on remote machine
6. `lpwd`: Print working directory on local machine
7. `ls`: List contents of remote directory
8. `get filename`: Retrieve a file
9. `mget filenames`: Retrieve multiple files
10. `put filename`: Send one file
11. `mput filenames`: Send multiple files
12. `prompt`: Toggle interactive prompting
13. `binary`: Set binary transfer mode
14. `ascii`: Set ASCII transfer mode
15. `bye` or `quit`: Exit ftp

## Examples

1. Connect to an FTP server:
   ```
   ftp ftp.example.com
   ```

2. Connect to an FTP server with a specific port:
   ```
   ftp ftp.example.com 2121
   ```

3. Connect with verbose output:
   ```
   ftp -v ftp.example.com
   ```

4. Connect without auto-login:
   ```
   ftp -n ftp.example.com
   ```

5. Once connected, log in:
   ```
   ftp> user username
   ftp> pass password
   ```

6. List files in the current remote directory:
   ```
   ftp> ls
   ```

7. Change to a different remote directory:
   ```
   ftp> cd /public_html
   ```

8. Download a file:
   ```
   ftp> get filename.txt
   ```

9. Download multiple files:
   ```
   ftp> mget *.txt
   ```

10. Upload a file:
    ```
    ftp> put localfile.txt
    ```

11. Upload multiple files:
    ```
    ftp> mput *.jpg
    ```

12. Change transfer mode to binary:
    ```
    ftp> binary
    ```

13. Change transfer mode to ASCII:
    ```
    ftp> ascii
    ```

14. Create a directory on the remote server:
    ```
    ftp> mkdir newdirectory
    ```

15. Remove a file from the remote server:
    ```
    ftp> delete filename.txt
    ```

16. Remove a directory from the remote server:
    ```
    ftp> rmdir olddirectory
    ```

17. Display the current remote working directory:
    ```
    ftp> pwd
    ```

18. Display the current local working directory:
    ```
    ftp> lpwd
    ```

19. Change the local working directory:
    ```
    ftp> lcd /path/to/local/directory
    ```

20. Toggle interactive prompting:
    ```
    ftp> prompt
    ```

21. Exit the FTP session:
    ```
    ftp> bye
    ```

## Common Use Cases

1. Uploading files to a web server
2. Downloading files from a remote server
3. Managing files on a remote server
4. Backing up data to a remote FTP server
5. Synchronizing files between local and remote systems

## Notes

- FTP transfers data in clear text, including passwords. For secure transfers, consider using SFTP or FTPS instead.
- Many modern systems are moving away from FTP due to security concerns. Check if your system supports more secure alternatives.
- The `ftp` command may not be installed by default on some systems. You might need to install it separately.
- Some FTP servers support anonymous login. Use "anonymous" as the username and your email as the password.
- The `binary` mode is crucial for transferring non-text files like images or executables to prevent corruption.
- Use `mget` and `mput` with caution, especially with wildcards, to avoid unintended file transfers.
- The `prompt` command is useful to toggle confirmation for each file when using `mget` or `mput`.
- Some FTP clients support scripting for automated tasks. Check your specific FTP client's documentation for details.

[Back to Linux Commands](../readme.md)
