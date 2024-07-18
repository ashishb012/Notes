# pwd Command Guide

## Basic Syntax

```
pwd [OPTION]...
```

## Purpose

The `pwd` command, which stands for "print working directory", is used to display the current working directory's full path. It shows the directory you are currently in within the filesystem hierarchy.

## Options

`pwd` has very few options:

1. `-L, --logical`: Use PWD from environment, even if it contains symlinks (default behavior)
2. `-P, --physical`: Avoid all symlinks and print the physical directory
3. `--help`: Display help information and exit
4. `--version`: Output version information and exit

## Examples

1. Basic usage (print current working directory):
   ```
   pwd
   ```
   Output might be something like: `/home/username/documents`

2. Use physical path, avoiding symlinks:
   ```
   pwd -P
   ```
   If your current directory involves symlinks, this might give a different output than the basic command.

3. Explicitly use logical path (usually unnecessary as it's the default):
   ```
   pwd -L
   ```

4. Display help information:
   ```
   pwd --help
   ```

5. Show version information:
   ```
   pwd --version
   ```

6. Using `pwd` in a script to get the current directory:
   ```bash
   #!/bin/bash
   current_dir=$(pwd)
   echo "The script is running from: $current_dir"
   ```

7. Combining with other commands:
   ```
   echo "Files in $(pwd):"
   ls -l
   ```

Remember that `pwd` is a built-in shell command in many shells (like bash), which means it may have slightly different behavior or options compared to the standalone `/bin/pwd` command. Always check your specific system's documentation for the most accurate information.
