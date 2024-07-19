# Comprehensive Guide to the 'scp' Command

The 'scp' (Secure Copy) command is used to securely copy files and directories between a local and a remote system, or between two remote systems. It uses SSH for data transfer and provides the same authentication and security as SSH.

## Basic Syntax

```
scp [OPTIONS] [[user@]host1:]file1 ... [[user@]host2:]file2
```

## Common Options

1. `-P port`: 
   Specifies the port to connect to on the remote host.

   Example:
   ```
   scp -P 2222 file.txt user@remote:/path/to/destination/
   ```

2. `-r`: 
   Recursively copy entire directories.

   Example:
   ```
   scp -r /local/directory user@remote:/path/to/destination/
   ```

3. `-p`: 
   Preserve modification times, access times, and modes from the original file.

   Example:
   ```
   scp -p file.txt user@remote:/path/to/destination/
   ```

4. `-q`: 
   Quiet mode: disables the progress meter as well as warning and diagnostic messages.

   Example:
   ```
   scp -q file.txt user@remote:/path/to/destination/
   ```

5. `-C`: 
   Enables compression.

   Example:
   ```
   scp -C large_file.zip user@remote:/path/to/destination/
   ```

6. `-i identity_file`: 
   Selects the file from which the identity (private key) for public key authentication is read.

   Example:
   ```
   scp -i ~/.ssh/my_private_key file.txt user@remote:/path/to/destination/
   ```

## Additional Options

7. `-3`: 
   Copies between two remote hosts are transferred through the local host.

8. `-4`: 
   Forces scp to use IPv4 addresses only.

9. `-6`: 
   Forces scp to use IPv6 addresses only.

10. `-B`: 
    Selects batch mode (prevents asking for passwords or passphrases).

11. `-F ssh_config`: 
    Specifies an alternative per-user SSH configuration file.

12. `-l limit`: 
    Limits the used bandwidth, specified in Kbit/s.

13. `-o ssh_option`: 
    Can be used to pass options to ssh in the format used in ssh_config.

14. `-S program`: 
    Name of program to use for the encrypted connection.

15. `-v`: 
    Verbose mode. Causes scp and ssh to print debugging messages about their progress.

## Usage Examples

1. Copy a file from local to remote:
   ```
   scp /path/to/local/file.txt user@remote:/path/to/remote/directory/
   ```

2. Copy a file from remote to local:
   ```
   scp user@remote:/path/to/remote/file.txt /path/to/local/directory/
   ```

3. Copy a directory recursively from local to remote:
   ```
   scp -r /path/to/local/directory user@remote:/path/to/remote/directory/
   ```

4. Copy a file between two remote hosts:
   ```
   scp user1@remote1:/path/to/file.txt user2@remote2:/path/to/destination/
   ```

5. Copy multiple files to a remote directory:
   ```
   scp file1.txt file2.txt user@remote:/path/to/remote/directory/
   ```

6. Use a specific port:
   ```
   scp -P 2222 file.txt user@remote:/path/to/destination/
   ```

7. Copy with compression:
   ```
   scp -C large_file.zip user@remote:/path/to/destination/
   ```

8. Preserve file attributes:
   ```
   scp -p file.txt user@remote:/path/to/destination/
   ```

9. Use a specific identity file:
   ```
   scp -i ~/.ssh/my_key file.txt user@remote:/path/to/destination/
   ```

10. Copy with verbose output:
    ```
    scp -v file.txt user@remote:/path/to/destination/
    ```

11. Limit bandwidth usage:
    ```
    scp -l 500 large_file.zip user@remote:/path/to/destination/
    ```

12. Use IPv4 only:
    ```
    scp -4 file.txt user@remote:/path/to/destination/
    ```

Remember that 'scp' relies on SSH, so you need to have SSH access to the remote system. Also, the remote system must have the scp program available. Always be cautious when copying files, especially when using recursive options, to avoid overwriting important data.
