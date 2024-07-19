# The `fg` Command

The `fg` command is used in Unix-like operating systems to bring background jobs to the foreground. It's a shell built-in command, typically used in job control.

## Basic Syntax

```
fg [job_spec]
```

## Options

The `fg` command, like `bg`, doesn't have many options itself. The main variation is in specifying which job to bring to the foreground.

1. **Without arguments**: 
   If no job specification is given, `fg` brings the most recently backgrounded job to the foreground.

2. **With job specification**:
   You can specify which job to bring to the foreground by using:
   - Job number (e.g., %1, %2)
   - Job name (e.g., %emacs)
   - Process ID (e.g., %12345)

## Examples

1. Bring the most recently backgrounded job to the foreground:
   ```
   $ fg
   ```

2. Bring a specific job to the foreground by job number:
   ```
   $ fg %2
   ```

3. Bring a job to the foreground by name:
   ```
   $ fg %emacs
   ```

4. Bring a job to the foreground by process ID:
   ```
   $ fg %12345
   ```

5. Start a background job and then bring it to the foreground:
   ```
   $ sleep 100 &
   [1] 12345
   $ fg
   sleep 100
   ```

6. Manage multiple jobs:
   ```
   $ sleep 100 &
   [1] 12345
   $ sleep 200 &
   [2] 12346
   $ jobs
   [1]-  Running                 sleep 100 &
   [2]+  Running                 sleep 200 &
   $ fg %1
   sleep 100
   [Ctrl+Z]  # Suspend the job
   [1]+  Stopped                 sleep 100
   $ fg %2
   sleep 200
   ```

## Related Commands

- `bg`: Resumes suspended jobs in the background
- `jobs`: Lists the active jobs
- `kill`: Sends a signal to a job or process
- `wait`: Waits for a background job to finish

## Notes

- The `fg` command is most useful in interactive shell sessions.
- When a job is brought to the foreground, it can receive input from the terminal.
- If the foreground job is stopped (e.g., with Ctrl+Z), you can use `bg` to resume it in the background or `fg` to bring it back to the foreground.
- The behavior of `fg` can vary slightly between different shells (e.g., bash, zsh, fish).
