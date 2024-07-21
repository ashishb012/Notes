# su Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `su` (switch user) command in Linux is used to run a shell or command as a different user. Its basic syntax is:

```
su [OPTIONS] [USERNAME]
```

If no username is specified, it defaults to the root user.

## Common Options

1. `-`, `-l`, `--login`: Provide an environment similar to a real login
2. `-c COMMAND`, `--command=COMMAND`: Pass a single command to the shell
3. `-s SHELL`, `--shell=SHELL`: Run the specified shell instead of the default
4. `-p`, `--preserve-environment`: Preserve the current environment variables
5. `-m`, `-P`, `--preserve-environment`: Same as `-p`
6. `--help`: Display help message and exit
7. `--version`: Output version information and exit

## Examples

1. Switch to root user:
   ```
   su
   ```
   You'll be prompted for the root password.

2. Switch to a specific user:
   ```
   su johndoe
   ```
   You'll be prompted for johndoe's password.

3. Switch to root with a login shell:
   ```
   su -
   ```
   This provides an environment similar to a direct root login.

4. Switch to another user with a login shell:
   ```
   su - johndoe
   ```

5. Run a single command as root:
   ```
   su -c "apt update"
   ```

6. Run a single command as another user:
   ```
   su -c "ls -l /home/johndoe" johndoe
   ```

7. Switch to root and preserve current environment:
   ```
   su -p
   ```

8. Use a specific shell when switching users:
   ```
   su -s /bin/zsh johndoe
   ```

9. Combine options:
   ```
   su -lc "whoami" johndoe
   ```
   This switches to johndoe with a login shell, runs 'whoami', and exits.

10. Switch to root and run multiple commands:
    ```
    su -c "apt update && apt upgrade -y"
    ```

11. Switch to another user and start a specific application:
    ```
    su -c "firefox" johndoe
    ```

12. Use su in a script to perform actions as another user:
    ```bash
    #!/bin/bash
    su -c "echo 'This is run as johndoe' > /home/johndoe/test.txt" johndoe
    ```

## Important Considerations

1. The `su` command requires you to know the password of the user you're switching to. This is different from `sudo`, which uses your own password.

2. Using `su -` or `su -l` is often preferred over plain `su`, as it provides a clean environment similar to a fresh login.

3. When using `su` to switch to root, it's generally recommended to use `sudo` instead, as it provides better auditing and control.

4. The `-c` option is useful for running single commands without fully switching to the other user's environment.

5. Be cautious when preserving the environment (`-p` or `-m`), as this can sometimes lead to unexpected behavior or security issues.

6. If you frequently need to run commands as root, consider configuring `sudo` access instead of using `su`.

7. Remember that when you use `su`, you're fully assuming the identity of the other user. Be careful, especially when switching to root.

8. The behavior of `su` can be affected by system configuration, particularly PAM (Pluggable Authentication Modules) settings.

Remember, while `su` is a powerful tool, it should be used judiciously. In many cases, `sudo` provides a more secure and flexible approach to running commands with elevated privileges.

[Back to Linux Commands](../readme.md)
