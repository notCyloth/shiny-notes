Remember to check for pages with extensions like .aspx, .php etc...
# Identify Server Type
Identify the server type based on HTTP response headers. For example: 
#### apache
- .php
#### IIS
- .asp
- .aspx
# Brute force index page
```
ffuf -w /usr/share/seclists/Discovery/Web-Content/web-extensions.txt:FUZZ -u http://$IP_ADDRESS:$PORT/indexFUZZ -mc 200
```
Once an extension is found, pages can be bruteforced with the -e 'extension' i.e. -e .php, so the wordlist will check the words with and without the extension.
# Check source code of page
Right click and check the source code of a page to see if it shows you the webpage extension.