# The `wget` Command

[Back to Linux Commands](../readme.md)

`wget` is a command-line utility for retrieving files using HTTP, HTTPS, and FTP protocols. It's non-interactive, meaning it can work in the background or in scripts.

## Basic Syntax

```
wget [options] [URL]
```

## Common Options

1. `-O file`: Save the downloaded file with a different name
2. `-P prefix`: Set directory prefix
3. `-c`: Continue partially downloaded files
4. `-r`: Download recursively (for websites)
5. `-np`: Do not ascend to the parent directory when downloading recursively
6. `-m`: Mirror website
7. `-A`: Accept list (comma-separated) of file extensions
8. `-R`: Reject list of file extensions
9. `-k`: Convert links for offline viewing
10. `-p`: Download all files necessary to properly display a page
11. `-U`: Set user agent string
12. `-l`: Maximum depth of recursion
13. `--limit-rate`: Limit the download speed
14. `-b`: Go to background immediately after startup
15. `-q`: Quiet mode (no output)
16. `-v`: Verbose mode (default)

## Examples

1. Basic download:
   ```
   wget https://example.com/file.zip
   ```

2. Download and save with a different name:
   ```
   wget -O newname.zip https://example.com/file.zip
   ```

3. Continue a partially downloaded file:
   ```
   wget -c https://example.com/largefile.iso
   ```

4. Download to a specific directory:
   ```
   wget -P /path/to/directory https://example.com/file.txt
   ```

5. Mirror an entire website:
   ```
   wget -m -k -p https://example.com
   ```

6. Download recursively with depth limit:
   ```
   wget -r -l 2 https://example.com
   ```

7. Download only specific file types:
   ```
   wget -r -A .pdf,.doc https://example.com
   ```

8. Reject specific file types:
   ```
   wget -r -R .png,.jpg https://example.com
   ```

9. Set download speed limit:
   ```
   wget --limit-rate=200k https://example.com/largefile.iso
   ```

10. Download in background:
    ```
    wget -b https://example.com/largefile.iso
    ```

11. Use a specific user agent:
    ```
    wget -U "Mozilla/5.0" https://example.com
    ```

12. Download files listed in a text file:
    ```
    wget -i file_list.txt
    ```

13. Specify username and password for HTTP authentication:
    ```
    wget --http-user=username --http-password=password https://example.com/private/file.zip
    ```

14. Create a complete local copy of a website:
    ```
    wget -m -p -k -E -np https://example.com
    ```

15. Download a file using FTP:
    ```
    wget ftp://ftp.example.com/file.zip
    ```

## Output Explanation

A typical `wget` output looks like this:

```
--2023-07-18 10:15:20--  https://example.com/file.zip
Resolving example.com (example.com)... 93.184.216.34
Connecting to example.com (example.com)|93.184.216.34|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1234567 (1.2M) [application/zip]
Saving to: 'file.zip'

file.zip            100%[===================>]   1.18M  1.18MB/s    in 1.0s    

2023-07-18 10:15:22 (1.18 MB/s) - 'file.zip' saved [1234567/1234567]
```

- First line: Start time and URL
- Following lines: DNS resolution and connection details
- `HTTP request sent`: Request sent and response received
- `Length`: File size
- Progress bar: Download progress
- Last line: Completion time, average speed, and final file size

## Common Use Cases

1. Downloading files from the internet
2. Mirroring websites for offline viewing
3. Recursive downloading of web content
4. Resuming interrupted downloads
5. Automating downloads in scripts
6. Web scraping (with caution and respect for website terms of service)

## Notes

- Always respect the website's `robots.txt` file and terms of service when using `wget`, especially for recursive downloads or web scraping.
- `wget` can be used in scripts for automated downloading tasks.
- For HTTPS URLs, `wget` verifies the certificate by default. Use `--no-check-certificate` to bypass this (not recommended for security reasons).
- `wget` can handle redirects, but you might need to use `--max-redirect` to control the number of redirects followed.
- The `-N` (or `--timestamping`) option is useful for keeping local copies of remote files up-to-date.

[Back to Linux Commands](../readme.md)
