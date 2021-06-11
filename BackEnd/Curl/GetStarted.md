# Get Started
See [Everything curl](https://everything.curl.dev/).
Or [curl Tutorial](https://curl.se/docs/httpscripting.html).

## Background
### What is Curl?
It is a client-side program, a URL client. So we call it CURL.

It makes the requests, it gets the data, it sends data and it retrieves the information.

### See the Protocol
Using curl's option `--verbose` (`-v` as a short option) will display what kind of commands curl sends to the server, 
as well as a few other informational texts.
```shell
curl -v http://www.google.com

*   Trying 142.251.33.68...
* TCP_NODELAY set
* Connected to www.google.com (142.251.33.68) port 80 (#0)
> GET / HTTP/1.1
> Host: www.google.com
> User-Agent: curl/7.64.1
> Accept: */*
```

### See the Response
By default curl sends the response to stdout. 
You need to redirect it somewhere to avoid that, most often that is done with `-o` or `-O`.
```shell
curl http://www.google.com -o Desktop/saved
```

## URL
