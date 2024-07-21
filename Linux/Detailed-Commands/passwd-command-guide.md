# passwd Command Guide: Options and Examples

The `passwd` command in Linux is used to change user account passwords and modify password attributes. Its basic syntax is:

```
passwd [OPTIONS] [USERNAME]
```

If no username is specified, it changes the password for the current user.

## Common Options

1. `-d, --delete`: Delete the password for the named account (root only)
2. `-e, --expire`: Expire the password for the named account (force user to change password next login)
3. `-i, --inactive DAYS`: Set the number of days after password expiration when an account becomes inactive
4. `-l, --lock`: Lock the named account (root only)
5. `-u, --unlock`: Unlock the named account (root only)
6. `-m, --mindays MIN_DAYS`: Set the minimum number of days between password changes
7. `-M, --maxdays MAX_DAYS`: Set the maximum number of days a password remains valid
8. `-n, --dry-run`: Don't update password tokens, just print what would happen
9. `-S, --status`: Display account status information
10. `-w, --warndays WARN_DAYS`: Set the number of days of warning before a password change is required
11. `-x, --maximum MAX_DAYS`: Same as --maxdays
12. `-k, --keep-tokens`: Keep authentication tokens and only change the password

## Examples

1. Change your own password:
   ```
   passwd
   ```
   You'll be prompted to enter your current password, then the new password twice.

2. Change another user's password (requires root privileges):
   ```
   sudo passwd johndoe
   ```

3. Delete a user's password (making it a no-password account):
   ```
   sudo passwd -d username
   ```

4. Lock a user account:
   ```
   sudo passwd -l username
   ```

5. Unlock a user account:
   ```
   sudo passwd -u username
   ```

6. Expire a user's password (force change on next login):
   ```
   sudo passwd -e username
   ```

7. Set the maximum password age:
   ```
   sudo passwd -M 90 username
   ```
   This sets the password to expire after 90 days.

8. Set the minimum password age:
   ```
   sudo passwd -m 7 username
   ```
   This prevents the password from being changed for 7 days.

9. Set password expiry warning:
   ```
   sudo passwd -w 7 username
   ```
   This will start warning the user 7 days before password expiration.

10. Display account status:
    ```
    sudo passwd -S username
    ```

11. Set account inactive days:
    ```
    sudo passwd -i 30 username
    ```
    The account will become inactive 30 days after password expiration.

12. Combine multiple options:
    ```
    sudo passwd -m 7 -M 90 -w 7 -i 30 username
    ```
    This sets minimum age (7 days), maximum age (90 days), warning period (7 days), and inactive period (30 days) all at once.

## Important Considerations

1. Regular users can only change their own passwords. Only root can change other users' passwords or modify password policies.

2. When changing passwords, most systems enforce password complexity rules. These rules can typically be configured in `/etc/security/pwquality.conf` or similar files.

3. The `-d` (delete password) option should be used with caution, as it allows login without a password.

4. Locking an account (`-l`) adds a '!' at the beginning of the encrypted password, preventing password-based login. This doesn't affect SSH key-based authentication.

5. The `-n` (dry-run) option is useful for seeing what changes would be made without actually applying them.

6. Changes to password policies (like min/max days) take effect at the next password change.

7. Always use `sudo` when changing another user's password or modifying password policies.

8. Be cautious when using `passwd` in scripts, as it typically requires interactive input. For scripting, consider using `chpasswd` instead.

Remember, password management is crucial for system security. Always use strong, unique passwords and follow your organization's password policies.
