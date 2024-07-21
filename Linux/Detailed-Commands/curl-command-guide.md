# curl Command Guide

[Back to Linux Commands](../readme.md)

## Basic Syntax

```
curl [options] [URL]
```

## Common Options

1. `-o, --output <file>`: Write output to a file instead of stdout
2. `-O, --remote-name`: Write output to a file named as the remote file
3. `-L, --location`: Follow redirects
4. `-i, --include`: Include the HTTP header in the output
5. `-I, --head`: Fetch the headers only
6. `-v, --verbose`: Make the operation more talkative
7. `-s, --silent`: Silent mode, don't show progress meter or error messages
8. `-u, --user <user:password>`: Server user and password
9. `-X, --request <command>`: Specify request method to use
10. `-H, --header <header>`: Pass custom header(s) to server
11. `-d, --data <data>`: HTTP POST data
12. `-F, --form <name=content>`: Specify HTTP multipart POST data
13. `-A, --user-agent <string>`: User-Agent to send to server
14. `-b, --cookie <data>`: Send cookies from string/file
15. `-c, --cookie-jar <filename>`: Write cookies to filename after operation
16. `-k, --insecure`: Allow insecure server connections when using SSL
17. `--max-time <seconds>`: Maximum time allowed for the transfer

## Examples

1. Basic GET request:
   ```
   curl https://example.com
   ```

2. Save output to a file:
   ```
   curl -o output.html https://example.com
   ```

3. Follow redirects:
   ```
   curl -L https://example.com
   ```

4. Include headers in the output:
   ```
   curl -i https://example.com
   ```

5. Send a POST request with data:
   ```
   curl -X POST -d "param1=value1&param2=value2" https://example.com/api
   ```

6. Send a POST request with JSON data:
   ```
   curl -X POST -H "Content-Type: application/json" -d '{"key1":"value1", "key2":"value2"}' https://example.com/api
   ```

7. Download a file and specify the output name:
   ```
   curl -O https://example.com/file.zip
   ```

8. Use basic authentication:
   ```
   curl -u username:password https://example.com/api
   ```

9. Send a custom header:
   ```
   curl -H "X-Custom-Header: value" https://example.com
   ```

10. Upload a file using POST:
    ```
    curl -F "file=@localfile.jpg" https://example.com/upload
    ```

11. Get only the HTTP headers of a URL:
    ```
    curl -I https://example.com
    ```

12. Set a user agent:
    ```
    curl -A "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3" https://example.com
    ```

13. Use a proxy:
    ```
    curl -x proxy.example.com:8080 https://example.com
    ```

14. Limit the rate of data transfer:
    ```
    curl --limit-rate 1000K -O https://example.com/largefile.zip
    ```

15. Resume a previous file transfer:
    ```
    curl -C - -O https://example.com/largefile.zip
    ```

These examples cover a wide range of use cases, but curl has many more options and capabilities. Always refer to the manual (`man curl`) or the official documentation for the most up-to-date and complete information.

[Back to Linux Commands](../readme.md)
