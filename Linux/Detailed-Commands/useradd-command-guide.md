# useradd Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `useradd` command in Linux is used to create a new user account or update default new user information. Its basic syntax is:

```
useradd [OPTIONS] USERNAME
```

## Common Options

1. `-m, --create-home`: Create the user's home directory
2. `-d, --home-dir HOME_DIR`: Specify home directory for the new user
3. `-s, --shell SHELL`: Specify login shell for the new user
4. `-g, --gid GROUP`: Specify the primary group for the new user
5. `-G, --groups GROUPS`: Specify supplementary groups
6. `-u, --uid UID`: Specify user ID for the new user
7. `-c, --comment COMMENT`: Add a comment (typically full name)
8. `-e, --expiredate DATE`: Set account expiration date
9. `-f, --inactive DAYS`: Set the number of days after password expires until account is disabled
10. `-k, --skel SKEL_DIR`: Use this alternative skeleton directory
11. `-M`: Do not create the user's home directory
12. `-N, --no-user-group`: Do not create a group with the same name as the user
13. `-r, --system`: Create a system account
14. `-p, --password PASSWORD`: Use encrypted password for the new account

## Examples

1. Basic user creation:
   ```
   sudo useradd johndoe
   ```
   This creates a new user 'johndoe' with default settings.

2. Create user with home directory:
   ```
   sudo useradd -m janedoe
   ```
   This creates a new user 'janedoe' and creates their home directory.

3. Specify home directory and shell:
   ```
   sudo useradd -m -d /home/custom_home -s /bin/bash newuser
   ```
   Creates 'newuser' with a custom home directory and bash as the login shell.

4. Create user with specific user ID and group ID:
   ```
   sudo useradd -u 1500 -g 1000 customuser
   ```
   Creates 'customuser' with UID 1500 and adds them to the group with GID 1000.

5. Add user to multiple groups:
   ```
   sudo useradd -G wheel,developers,docker newdev
   ```
   Creates 'newdev' and adds them to the specified supplementary groups.

6. Create system account:
   ```
   sudo useradd -r sysuser
   ```
   Creates a system account 'sysuser' (typically for daemons or services).

7. Set account expiration:
   ```
   sudo useradd -e 2024-12-31 tempuser
   ```
   Creates 'tempuser' with an account expiration date of December 31, 2024.

8. Create user with comment:
   ```
   sudo useradd -c "John Doe from Accounting" jdoe
   ```
   Creates 'jdoe' with a comment (usually used for full name).

9. Create user without creating home directory:
   ```
   sudo useradd -M nohomeuser
   ```
   Creates 'nohomeuser' without creating a home directory.

10. Create user with specific skeleton directory:
    ```
    sudo useradd -m -k /etc/custom_skel newuser
    ```
    Creates 'newuser' using a custom skeleton directory for the home directory contents.

11. Create user with encrypted password:
    ```
    sudo useradd -p $(openssl passwd -1 "password123") secureuser
    ```
    Creates 'secureuser' with an encrypted password. Note: Setting passwords this way is generally not recommended for security reasons.

Remember to use `sudo` with `useradd` as it requires root privileges. Also, after creating a user, you might want to set a password using the `passwd` command.

Note: The exact behavior and available options of `useradd` can vary slightly between different Linux distributions. Always check your system's man pages (`man useradd`) for the most accurate information for your specific system.

[Back to Linux Commands](../readme.md)
