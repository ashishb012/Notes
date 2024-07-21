# userdel Command Guide: Options and Examples

[Back to Linux Commands](../readme.md)

The `userdel` command in Linux is used to delete a user account and related files. Its basic syntax is:

```
userdel [OPTIONS] USERNAME
```

## Common Options

1. `-r, --remove`: Remove home directory and mail spool
2. `-f, --force`: Force removal of files, even if not owned by user
3. `-Z, --selinux-user`: Remove any SELinux user mapping for the user's login

## Examples

1. Basic user deletion:
   ```
   sudo userdel johndoe
   ```
   This deletes the user 'johndoe' but leaves their home directory and files intact.

2. Delete user and remove home directory:
   ```
   sudo userdel -r janedoe
   ```
   This deletes the user 'janedoe' and removes their home directory and mail spool.

3. Force deletion of user and their files:
   ```
   sudo userdel -f -r problematicuser
   ```
   This forcibly deletes 'problematicuser', their home directory, and all their files, even if some aren't owned by the user.

4. Delete user and remove SELinux user mapping:
   ```
   sudo userdel -Z selinuxuser
   ```
   This deletes 'selinuxuser' and removes any SELinux user mapping for their login.

5. Attempt to delete a currently logged-in user:
   ```
   sudo userdel activeuser
   ```
   This will likely fail with a message that the user is currently logged in. You may need to force logout the user first.

6. Delete user from a specific passwd file (useful in chroot environments):
   ```
   sudo userdel -f chrootuser --prefix /path/to/chroot
   ```
   This deletes 'chrootuser' from the passwd file in the specified chroot environment.

## Important Considerations

1. Always use `sudo` or run as root, as `userdel` requires administrative privileges.

2. Be extremely cautious with the `-f` (force) option, as it can lead to unintended data loss.

3. If you're unsure, it's often safer to first disable a user account (using `usermod -L username`) rather than deleting it entirely.

4. The `-r` option doesn't always remove all files owned by the user in all locations. You may need to manually check and remove files outside the home directory.

5. If the user is a member of any groups, you may need to manually remove them from these groups if you want to clean up completely.

6. Some systems use `userdel` as a frontend to distribution-specific tools. Always check your system's man pages (`man userdel`) for the most accurate information.

7. Be very careful when deleting system users (UIDs < 1000 on many systems), as this can break system functionality.

Remember, deleting a user account is a significant action and should be done with caution, especially on production systems.

[Back to Linux Commands](../readme.md)
