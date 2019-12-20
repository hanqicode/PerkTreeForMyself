## HTTP
HTTP is implemented in two programs: a client program and a server program.

HTTP defines how Web clients request Web pages from Web servers and how servers transfer Web pages to clients.

HTTP uses TCP as its underlying transport protocol.

Because an HTTP server maintains no information about the clients, HTTP is said to be a **stateless protocol**.

### Non-Persistent Connections VS Persistent Connections
Although HTTP uses persistent connections in its default mode, HTTP clients and servers can be configured to use non-persistent connections instead.

#### HTTP with Non-Persistent Connections  
1. First, a brand-new connec- tion must be established and maintained for each requested object.
2. Each object suffers a delivery delay of two Round-Trip Time(RTTs) - one RTT to establish the TCP connection and one RTT to request and receive an object.

#### HTTP with Persistent Connections  
1. Typically, the HTTP server closes a connection when it isn’t used for a certain time.

### HTTP Request

A sample HTTP request:  
(A request message can have many more lines or as few as one line.)
```
GET /somedir/page.html HTTP/1.1 // **request line**

Host: www.someschool.edu        // **header lines 1**
Connection: close               // **header lines 2**
User-agent: Mozilla/5.0         // **header lines 3**
Accept-language: fr             // **header lines 4**

xxx                             // **entity body**
```

For request line:
1. the method field (`GET`, `POST`, `HEAD`, `PUT`,and `DELETE`)
2. the URL field
3. the HTTP version field

#### GET VS POST
GET: The GET method is used when the browser requests an object, with the requested object identified in the URL field.

POST: An HTTP client often uses the POST method when the user fills out a form.  
With a POST message, the user is still requesting a Web page from the server, 
but the specific contents of the Web page depend on what the user entered into the form fields.  
If the value of the method field is POST, then the **entity body** contains what the user entered into the form fields.

### HTTP Response

A sample HTTP response:
```
HTTP/1.1 200 OK                                 // **status line**

Connection: close                               // **header lines 1**
Date: Tue, 09 Aug 2011 15:44:04 GMT             // **header lines 2**
Server: Apache/2.2.3 (CentOS)                   // **header lines 3**
Last-Modified: Tue, 09 Aug 2011 15:11:03 GMT    // **header lines 4**
Content-Length: 6821                            // **header lines 5**
Content-Type: text/html                         // **header lines 6**

(data data data data data ...)                  // **entity body**
```

For status line:
1. the protocol version field
2. a status code
3. a corresponding status message

For response status code and status message:
```
200 OK: Request succeeded and the information is returned in the response.
400 Bad Request: This is a generic error code indicating that the request could not be understood by the server.
404 Not Found: The requested document does not exist on this server.
505 HTTP Version Not Supported: The requested HTTP protocol version is not supported by the server.
```

### Cookies
Cookie technology has four components:
1. a cookie header line in the HTTP response message; 
2. a cookie header line in the HTTP request message;
3. a cookie file kept on the user’s end system and managed by the user’s browser;
4. a back-end database at the Web site.

Cookies can thus be used to create a user session layer on top of stateless HTTP. 

### Web Caching
The Web cache(proxy server as a **intermediary between client and server**) has its own disk storage and keeps copies of recently requested objects in this storage.

Once a browser is configured, each browser request for an object is first directed to the Web cache.

For web cache:  
When it receives requests from and sends responses to a browser, it is a server.   
When it sends requests to and receives responses from an origin server, it is a client.

