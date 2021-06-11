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

### Spec
The Uniform Resource Locator(URL) format is how you specify the address of a particular resource on the Internet.
And yeah, the formal name is not URL, it is URI.

### Host
The host name is usually resolved using DNS or your `/etc/hosts` file to an IP address 
and that's what curl will communicate with.

## Fetch a Page

### GET
```shell
curl https://curl.se
```
The URL could itself refer to a web page, an image or a file.
The client issues a GET request to the server and receives the document it asked for.

## HTML forms

### GET
```html
<form method="GET" action="junk.cgi">
  <input type=text name="birthyear">
  <input type=submit name=press value="OK">
</form>
```

To make curl do the GET form post for you, just enter the expected created URL:
```shell
curl "http://www.example.com/when/junk.cgi?birthyear=1905&press=OK"
```

### POST
The GET method makes all input field names get displayed in the URL field of your browser. 
That's generally a good thing when you want to be able to bookmark that page with your given data, 
but it is an obvious disadvantage if you entered secret information in one of the fields or 
if there are a large amount of fields creating a very long and unreadable URL.

The HTTP protocol then offers the POST method. 
This way the client sends the data separated from the URL and thus you won't see any of it in the URL address field.

```html
<form method="POST" action="junk.cgi">
  <input type=text name="birthyear">
  <input type=submit name=press value=" OK ">
</form>
```

And to use curl to post this form with the same data filled in as before, we could do it like:
```shell
curl --data "birthyear=1905&press=%20OK%20" http://www.example.com/when.cgi
```

Note:
> The data you send to the server MUST already be properly encoded, curl will not do that for you.

Recent curl versions can in fact url-encode POST data for you, like this:
```shell
curl --data-urlencode "name=I am Daniel" http://www.example.com
```

