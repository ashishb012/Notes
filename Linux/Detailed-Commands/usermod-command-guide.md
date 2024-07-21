# usermod Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `usermod` command in Linux is used to modify a user account. It allows you to change various attributes of an existing user. Its basic syntax is:

```
usermod [OPTIONS] USERNAME
```

## Common Options

1. `-c, --comment COMMENT`: Change the user's full name or description
2. `-d, --home HOME_DIR`: Change the user's home directory
3. `-e, --expiredate EXPIRE_DATE`: Set account expiration date
4. `-f, --inactive INACTIVE`: Set the number of days after password expires until account is disabled
5. `-g, --gid GROUP`: Change the user's primary group
6. `-G, --groups GROUPS`: Set supplementary groups (replaces current groups)
7. `-a, --append`: Use with -G to add to supplementary groups instead of replacing
8. `-l, --login NEW_LOGIN`: Change the user's login name
9. `-L, --lock`: Lock the user's password (disable account)
10. `-U, --unlock`: Unlock the user's password
11. `-m, --move-home`: Move the content of the user's home directory to a new location (use with -d)
12. `-s, --shell SHELL`: Change the user's login shell
13. `-u, --uid UID`: Change the user ID
14. `-p, --password PASSWORD`: Change the user's password (encrypted)

## Examples

1. Change a user's comment (full name):
   ```
   sudo usermod -c "John Doe" johnd
   ```

2. Change a user's home directory:
   ```
   sudo usermod -d /newhome/janedoe janedoe
   ```

3. Move a user's home directory content:
   ```
   sudo usermod -m -d /newhome/janedoe janedoe
   ```

4. Set account expiration date:
   ```
   sudo usermod -e 2024-12-31 tempuser
   ```

5. Change a user's primary group:
   ```
   sudo usermod -g developers johnd
   ```

6. Add a user to supplementary groups:
   ```
   sudo usermod -aG docker,sudo janedoe
   ```

7. Change a user's login name:
   ```
   sudo usermod -l john_doe johnd
   ```

8. Lock a user account:
   ```
   sudo usermod -L problematicuser
   ```

9. Unlock a user account:
   ```
   sudo usermod -U rehabilitateduser
   ```

10. Change a user's login shell:
    ```
    sudo usermod -s /bin/bash johnd
    ```

11. Change a user's UID:
    ```
    sudo usermod -u 1001 johnd
    ```

12. Set password expiry information:
    ```
    sudo usermod -f 7 johnd
    ```
    This sets the account to be disabled 7 days after the password expires.

13. Replace all supplementary groups:
    ```
    sudo usermod -G group1,group2 johnd
    ```
    This replaces all of johnd's supplementary groups with group1 and group2.

14. Change multiple attributes at once:
    ```
    sudo usermod -c "John Doe" -g developers -G docker,sudo -s /bin/zsh johnd
    ```
    This changes John's comment, primary group, adds supplementary groups, and changes the login shell.

## Important Considerations

1. Always use `sudo` or run as root, as `usermod` requires administrative privileges.

2. Be cautious when changing UIDs or home directories, as this can affect file ownership and access.

3. When changing a username with `-l`, related changes (like home directory name) are not automatically made.

4. The `-G` option replaces all current supplementary groups. Use `-aG` to add groups without removing current ones.

5. Locking an account (`-L`) only prevents login via password. SSH key-based authentication may still work.

6. Changes made with `usermod` take effect at the user's next login.

7. Always check your system's man pages (`man usermod`) for the most accurate information for your specific system.

Remember, modifying user accounts can have significant impacts on system access and functionality. Always double-check your commands, especially in production environments.

[Back to Linux Commands](../readme.md)
