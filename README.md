# securityheaders
Python script to check HTTP security headers

Same functionality as securityheaders.io but as Python script. Also checks some server/version headers. Written and tested using Python 3.4.

With minor modifications could be used as a library for other projects.

### Usage
```
$ python3.6 securityheaders.py --help
usage: securityheaders.py [-h] [--max-redirects N] URL

Check HTTP security headers

positional arguments:
  URL                Target URL

optional arguments:
  -h, --help         show this help message and exit
  --max-redirects N  Max redirects, set 0 to disable (default: 2)
$
```

### Output
```
$ python3.6 securityheaders.py https://www.google.com

Missing or insecure headers:

    [ WARN ] X-Frame-Options is missing
    [ WARN ] Strict-Transport-Security is missing
    [  OK  ] Access-Control-Allow-Origin is missing
    [ WARN ] Content-Security-Policy is missing
    [ WARN ] X-Xss-Protection is missing
    [ WARN ] X-Content-Type-Options is missing
    [  OK  ] X-Powered-By is missing
    [  OK  ] Server is missing

Other security results:

    [  OK  ] HTTPS supported
    [  OK  ] HTTPS valid certificate
    [ FAIL ] HTTP -> HTTPS redirect
$
```
