# The `jobs` Command

[Back to Linux Commands](../readme.md)

The `jobs` command is used in Unix-like operating systems to display the status of jobs in the current shell session. It's a shell built-in command, typically used in job control.

## Basic Syntax

```
jobs [options] [job_spec]
```

## Options

The `jobs` command has several options:

1. `-l` (long format): Lists process IDs in addition to the normal information.
2. `-p` (process IDs): Lists only the process ID of the job's process group leader.
3. `-n` (new data): Displays only jobs that have changed status since last notification.
4. `-r` (running): Restricts output to running jobs.
5. `-s` (stopped): Restricts output to stopped jobs.

## Examples

1. List all jobs:
   ```
   $ jobs
   ```

2. List jobs with process IDs (long format):
   ```
   $ jobs -l
   ```

3. List only process IDs of jobs:
   ```
   $ jobs -p
   ```

4. List only running jobs:
   ```
   $ jobs -r
   ```

5. List only stopped jobs:
   ```
   $ jobs -s
   ```

6. Combine options (e.g., list running jobs with process IDs):
   ```
   $ jobs -lr
   ```

7. Start multiple jobs and use `jobs` to monitor them:
   ```
   $ sleep 100 &
   [1] 12345
   $ sleep 200 &
   [2] 12346
   $ long_running_process &
   [3] 12347
   $ jobs
   [1]   Running                 sleep 100 &
   [2]-  Running                 sleep 200 &
   [3]+  Running                 long_running_process &
   ```

8. Use `jobs` after suspending a foreground process:
   ```
   $ sleep 300
   [Ctrl+Z]
   [1]+  Stopped                 sleep 300
   $ jobs
   [1]+  Stopped                 sleep 300
   ```

9. Use job specification with `jobs`:
   ```
   $ jobs %1
   [1]+  Stopped                 sleep 300
   ```

## Job Status Indicators

- `+`: Indicates the default job (the one that would be foregrounded by `fg` or backgrounded by `bg` without arguments).
- `-`: Indicates the job that would become the default job when the current default job terminates.

## Related Commands

- `fg`: Brings a background job to the foreground
- `bg`: Resumes suspended jobs in the background
- `kill`: Sends a signal to a job or process
- `wait`: Waits for a background job to finish

## Notes

- The `jobs` command is most useful in interactive shell sessions.
- It's often used in conjunction with `fg` and `bg` for job control.
- The exact output format may vary slightly between different shells (e.g., bash, zsh, fish).
- In most shells, you can also use `%n` (where n is the job number) to refer to a specific job in other commands.

[Back to Linux Commands](../readme.md)
