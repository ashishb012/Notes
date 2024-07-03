# Git Tag Command Guide

The basic syntax of `git tag` is:

```
git tag [<options>] [<tagname>] [<commit>]
```

## Common Uses

1. `git tag`: List all tags
2. `git tag <tagname>`: Create a lightweight tag
3. `git tag -a <tagname> -m "<message>"`: Create an annotated tag
4. `git tag -d <tagname>`: Delete a tag
5. `git push origin <tagname>`: Push a tag to remote

## Subcommands and Their Options

### Listing Tags

```
git tag [<options>]
```

Options:
- `-l`, `--list`: List tags (optional, as it's the default operation)
- `--sort=<key>`: Sort tags by a specific key (e.g., `-v:refname` for version sort)
- `--format=<format>`: Format the tag listing
- `-n[<num>]`: Print <num> lines of each tag message
- `--contains [<commit>]`: Only list tags which contain the specified commit
- `--points-at <object>`: Only list tags of the given object
- `--column[=<options>]`, `--no-column`: Display tag listing in columns

Example:
```
git tag --list --sort=-v:refname
```

### Creating Tags

#### Lightweight Tags

```
git tag <tagname> [<commit>]
```

#### Annotated Tags

```
git tag -a <tagname> -m "<message>" [<commit>]
```

Options:
- `-a`, `--annotate`: Create an annotated tag
- `-m <msg>`, `--message=<msg>`: Tag message
- `-F <file>`, `--file=<file>`: Read message from file
- `-e`, `--edit`: Open editor for tag message
- `-s`, `--sign`: Make a GPG-signed tag
- `--cleanup=<mode>`: Cleanup the tag message

Example:
```
git tag -a v1.4 -m "Release version 1.4"
```

### Deleting Tags

```
git tag -d <tagname>...
```

Options:
- `-d`, `--delete`: Delete one or more tags

Example:
```
git tag -d v1.4 v1.5
```

### Verifying Tags

```
git tag -v [<tagname>]
```

Options:
- `-v`, `--verify`: Verify the GPG signature of tags

Example:
```
git tag -v v1.4.2
```

### Pushing Tags

While not strictly part of the `git tag` command, pushing tags is a common related operation:

```
git push [<remote>] --tags
git push [<remote>] <tagname>
```

Example:
```
git push origin v1.5
```

## Additional Options

- `--contains [<commit>]`: Only list tags which contain the specified commit
- `--no-contains [<commit>]`: Only list tags which don't contain the specified commit
- `--points-at <object>`: Only list tags of the given object
- `--merged [<commit>]`: Only list tags whose commits are reachable from the specified commit
- `--no-merged [<commit>]`: Only list tags whose commits are not reachable from the specified commit
- `--color[=<when>]`: Respect color.ui configuration
- `-i`, `--ignore-case`: Sorting and filtering tags are case insensitive

## Best Practices

1. Use annotated tags for releases, as they contain extra meta information like the tagger name, email, and date.
2. Use semantic versioning for tag names (e.g., v1.0.0, v2.1.3).
3. Always push tags explicitly to the remote after creating them locally.
4. Use lightweight tags for private or temporary reference points.

Remember, tags in Git are not automatically pushed to remote repositories. You need to explicitly push them using `git push --tags` or `git push <remote> <tagname>`.

Always refer to the official Git documentation for the most up-to-date and comprehensive information.
