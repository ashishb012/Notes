# SSH Command Guide

## Basic Syntax

```
ssh [options] [user@]hostname [command]
```

## Purpose

The `ssh` command is used to securely log into remote systems and execute commands on those systems. It provides encrypted communication between two untrusted hosts over an insecure network.

## Common Options

1. `-p port`: Specify the port to connect to on the remote host (default is 22)
2. `-i identity_file`: Selects a file from which the identity (private key) for public key authentication is read
3. `-l login_name`: Specifies the user to log in as on the remote machine
4. `-v`: Verbose mode, prints debugging messages about its progress
5. `-q`: Quiet mode, suppresses most warning and diagnostic messages
6. `-X`: Enables X11 forwarding
7. `-Y`: Enables trusted X11 forwarding
8. `-C`: Requests compression of all data
9. `-f`: Requests ssh to go to background just before command execution
10. `-N`: Do not execute a remote command (useful for just forwarding ports)
11. `-L`: Specifies that connections to the given TCP port on the local host are to be forwarded to the given host and port on the remote side
12. `-R`: Specifies that connections to the given TCP port on the remote host are to be forwarded to the local side
13. `-D`: Specifies a local "dynamic" application-level port forwarding
14. `-A`: Enables forwarding of the authentication agent connection
15. `-t`: Force pseudo-terminal allocation

## Examples

1. Basic SSH connection:
   ```
   ssh username@remote_host
   ```

2. Connect to a specific port:
   ```
   ssh -p 2222 username@remote_host
   ```

3. Use a specific identity file:
   ```
   ssh -i ~/.ssh/my_key username@remote_host
   ```

4. Enable X11 forwarding:
   ```
   ssh -X username@remote_host
   ```

5. Use compression:
   ```
   ssh -C username@remote_host
   ```

6. Run a command on the remote system without logging in:
   ```
   ssh username@remote_host 'ls -l'
   ```

7. Use verbose mode for debugging:
   ```
   ssh -v username@remote_host
   ```

8. Forward a local port to a remote port:
   ```
   ssh -L 8080:localhost:80 username@remote_host
   ```

9. Forward a remote port to a local port:
   ```
   ssh -R 8080:localhost:80 username@remote_host
   ```

10. Create a SOCKS proxy:
    ```
    ssh -D 1080 username@remote_host
    ```

11. Keep the connection alive by sending a signal periodically:
    ```
    ssh -o ServerAliveInterval=60 username@remote_host
    ```

12. Use multiple hop SSH (proxy jump):
    ```
    ssh -J user1@host1 user2@host2
    ```

13. Copy SSH public key to remote host:
    ```
    ssh-copy-id username@remote_host
    ```

14. Use SSH agent forwarding:
    ```
    ssh -A username@remote_host
    ```

15. Force pseudo-terminal allocation:
    ```
    ssh -t username@remote_host
    ```

Remember to always consult the manual (`man ssh`) or the official documentation for the most up-to-date and complete information, as SSH implementations and options may vary slightly between systems.
