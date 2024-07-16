# Project Information

## What is HTTP?
HTTP stands for Hypertext Transfer Protocol. It is a set of rule which is used for transferring the files like, audio, video, graphic image, text and other multimedia files on the WWW (World Wide Web). HTTP is a protocol that is used to transfer the hypertext from the client end to the server end, but HTTP does not have any security. Whenever a user opens their Web Browser, that means the user indirectly uses HTTP.

## What are HTTP Request Messages?
HTTP Requests are messages which are sent by the client or user to initiate an action on the server.

It consists of various things:

- **a**. Request Line: The Request-Line starts with a method token, which is followed by the Request-URI, the protocol version, and ending with CRLF. Using the SP characters, the elements are separated.

Syntax

Request-Line = Method SP Request-URI SP HTTP-Version CRLF  
- **b**. The Resource Identified by a Request:

- **c**. Request Header Fields:The request-header fields are used to allow the client to pass additional information to the server like the request and the client itself. The request header fields act as request modifiers, with semantics equivalent to the parameters on a programming language method invocation.

## What are HTTP Request Methods?
- **GET** : This method retrieves information from the given server using a given URI. GET request can retrieve the data. It cannot apply other effects on the data.

**HEAD** : The HEAD method is the same as the GET method. It is used to transfer the status line and header section only.

- **POST** : The POST request sends the data to the server. For example, file upload, customer information, etc. using the HTML forms.

- **PUT** : The PUT method is used to replace all the current representations of the target resource with the uploaded content.

- **DELETE** : The DELETE method is used to remove all the current representations of the target resource, which is given by URI.

- **CONNECT** : The CONNECT method is used to establish a tunnel to the server, which is identified by a given URI.


## Question 1: What is package.json file?
The `package.json` file stores the details of our project related to coding such as:
- Project name
- Version of the project
- Git repository
- Commands
- List of installed packages


## Question 2: Is Node.js single-threaded or multi-threaded?
Node.js is single-threaded.

## Question 3: Explain the difference between single-threaded and multi-threaded.
- **Single-threaded**: Runs one command at a time.
- **Multi-threaded**: Can run more than one command at a time.

## Question 4: What will you do if the node_modules folder of your project is deleted?
Just run the command `npm install` and it will recreate all the packages inside a `node_modules` folder that are listed inside the `package.json` file.

## Question 5: Should we push the node_modules folder to GitHub?
No, because the `node_modules` folder is very large and pushing it to GitHub can waste a lot of time. Instead, mention its path inside the `.gitignore` file and then push your code.

## What is the Status Code?
The Server issues an HTTP Status Code in response to a request of the client made to the server. Status code is a 3-digit integer. The first digit of status code is used to specify one of five standard classes of responses. The last two digits of status code do not have any categorization role.


# HTTP Status Codes

HTTP status codes are divided into five categories, each represented by the first digit of the three-digit code. Here are all the standard HTTP status codes:

## 1xx: Informational
- **100 Continue**: The server has received the request headers and the client should proceed to send the request body.
- **101 Switching Protocols**: The requester has asked the server to switch protocols and the server has agreed to do so.
- **102 Processing (WebDAV)**: The server has received and is processing the request, but no response is available yet.
- **103 Early Hints**: Used to return some response headers before final HTTP message.



## 2xx: Success
- **200 OK**: The request has succeeded.
- **201 Created**: The request has been fulfilled and resulted in a new resource being created.
- **202 Accepted**: The request has been accepted for processing, but the processing has not been completed.
- **203 Non-Authoritative Information**: The server successfully processed the request, but is returning information that may be from another source.
- **204 No Content**: The server successfully processed the request, but is not returning any content.
- **205 Reset Content**: The server successfully processed the request, but is not returning any content and requires that the requester reset the document view.
- **206 Partial Content**: The server is delivering only part of the resource due to a range header sent by the client.
- **207 Multi-Status (WebDAV)**: The message body that follows is an XML message and can contain a number of separate response codes.
- **208 Already Reported (WebDAV)**: The members of a DAV binding have already been enumerated in a previous reply to this request and are not being included again.
- **226 IM Used**: The server has fulfilled a request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.



## 3xx: Redirection
- **300 Multiple Choices**: Indicates multiple options for the resource that the client may follow.
- **301 Moved Permanently**: This and all future requests should be directed to the given URI.
- **302 Found**: 302 Found redirect status response code indicates that the resource requested has been temporarily moved to the URL given by the Location header
- **303 See Other**: a response indicating that the requested resource has been moved to a new location and the client should make a new request to that location.
- **304 Not Modified**:  the requested resource has not been modified since the last time it was loaded, and there's no need to transfer it again
- **305 Use Proxy (deprecated)**: The requested resource is available only through a proxy, the address for which is provided in the response.
- **306 Switch Proxy (unused)**: No longer used, but the code is reserved.
- **307 Temporary Redirect**: informs your browser that the requested content is temporarily located in another place
- **308 Permanent Redirect**: tells browsers and search engines that a resource has permanently moved to a new URL

## Difference between 302 vs 307 for Temporary Redirects?
A 302 redirect lets browsers use a different request from the original request. Whereas a 307 redirect requires the same request method for both the original request and the redirect.

This means that with a 302 redirect, visitors may use POST requests on the original page, and they can switch to GET method on the redirected page. On the other hand, a 307 redirect would force them to keep using POST.


## 4xx: Client Errors
- **400 Bad Request**: The server cannot or will not process the request due to an apparent client error.
- **401 Unauthorized**: Similar to 403 Forbidden, but specifically for use when authentication is required and has failed or has not yet been provided. or the client request has not been completed because it lacks valid authentication credentials for the requested resource.
- **402 Payment Required**: Reserved for future use.
- **403 Forbidden**: The request was valid, but the server is refusing action. The user might not have the necessary permissions for a resource.
- **404 Not Found**: The requested resource could not be found but may be available in the future. or  response status code indicates that the server cannot find the requested resource. Links that lead to a 404 page are often called broken or dead links and can be subject to link rot.
or A 404 status code only indicates that the resource is missing: not whether the absence is temporary or permanent.
- **405 Method Not Allowed**: A request method is not supported for the requested resource.
- **406 Not Acceptable**: The requested resource is capable of generating only content not acceptable according to the Accept headers sent in the request.
- **407 Proxy Authentication Required**: The client must first authenticate itself with the proxy.
- **408 Request Timeout**: The server timed out waiting for the request.
- **409 Conflict**: Indicates that the request could not be processed because of conflict in the request, such as an edit conflict.
- **410 Gone**: Indicates that the resource requested is no longer available and will not be available again.
- **411 Length Required**: The request did not specify the length of its content, which is required by the requested resource.
- **412 Precondition Failed**: The server does not meet one of the preconditions that the requester put on the request.
- **413 Payload Too Large**: The request is larger than the server is willing or able to process.
- **414 URI Too Long**: The URI provided was too long for the server to process.
- **415 Unsupported Media Type**: The request entity has a media type which the server or resource does not support.
- **416 Range Not Satisfiable**: The client has asked for a portion of the file (byte serving), but the server cannot supply that portion.
- **417 Expectation Failed**: The server cannot meet the requirements of the Expect request-header field.
- **418 I'm a teapot (RFC 2324, April Fools' joke)**: The server refuses to brew coffee because it is a teapot.
- **421 Misdirected Request**: The request was directed at a server that is not able to produce a response.
- **422 Unprocessable Entity (WebDAV)**: The request was well-formed but was unable to be followed due to semantic errors.
- **423 Locked (WebDAV)**: The resource that is being accessed is locked.
- **424 Failed Dependency (WebDAV)**: The request failed due to failure of a previous request.
- **425 Too Early**: Indicates that the server is unwilling to risk processing a request that might be replayed.
- **426 Upgrade Required**: The client should switch to a different protocol.
- **428 Precondition Required**: The origin server requires the request to be conditional.
- **429 Too Many Requests**: The user has sent too many requests in a given amount of time ("rate limiting").
- **431 Request Header Fields Too Large**: The server is unwilling to process the request because either an individual header field, or all the header fields collectively, are too large.
- **451 Unavailable For Legal Reasons**: The server is denying access to the resource as a consequence of a legal demand.



## 5xx: Server Errors
- **500 Internal Server Error**: A generic error message, given when an unexpected condition was encountered and no more specific message is suitable.
- **501 Not Implemented**: The server either does not recognize the request method, or it lacks the ability to fulfill the request.
- **502 Bad Gateway**: The server was acting as a gateway or proxy and received an invalid response from the upstream server.
- **503 Service Unavailable**: The server is currently unavailable (because it is overloaded or down for maintenance).
- **504 Gateway Timeout**: The server was acting as a gateway or proxy and did not receive a timely response from the upstream server.
- **505 HTTP Version Not Supported**: The server does not support the HTTP protocol version used in the request.
- **506 Variant Also Negotiates**: Transparent content negotiation for the request results in a circular reference.
- **507 Insufficient Storage (WebDAV)**: The server is unable to store the representation needed to complete the request.
- **508 Loop Detected (WebDAV)**: The server detected an infinite loop while processing a request.
- **510 Not Extended**: Further extensions to the request are required for the server to fulfill it.
- **511 Network Authentication Required**: The client needs to authenticate to gain network access.





## What are Persistent Connections?
In HTTP/1.0, the connection is closed after a single request or response pair. In HTTP/1.1, a mechanism was introduced, which is known as keep-alive-mechanism. In this mechanism, a connection could be reused for more than one request.

## What is Session State in HTTP?
Session state is also known as Stateless state. HTTP is a stateless protocol. In the session state, the client and server just know about each other only during the current request. If the connection is closed, and two computers want to connect again, they need to provide information to each other as a new connection, and the connection is handled as the very first one.

## What is HTTP Message?
HTTP Message is used to show how data is exchanged between the client and the server. It is based on a client-server architecture. An HTTP client is a program that establishes a connection to a server to send one or more HTTP request messages. An HTTP server is a program that accepts connections to serve HTTP requests by sending an HTTP response messages.

## What is HTTP cURL?
HTTP cURL is a command-line tool. It is available on all major operating systems

## What is HTTP Response?
HTTP Response sent by a server to the client. The response is used to provide the client with the resource it requested. It is also used to inform the client that the action requested has been carried out. It can also inform the client that an error occurred in processing its request.

An HTTP response contains the following things:

Status Line
Response Header Fields or a series of HTTP headers
3Message Body
## What is HTTP Security?
HTTP is used to communicate over the internet, so users, information providers, and application developers should be aware of the limitations of security in HTTP/1.1. There are two methods to establish a secure HTTP connection: https URI scheme and the HTTP/1.1 Upgrade header.


## Can you explain how HTTPS works and why it’s considered secure?.
HTTPS, short for Hypertext Transfer Protocol Secure, is a protocol used for secure communication over a computer network. It uses encryption to ensure data integrity and confidentiality. HTTPS operates through two main protocols: HTTP and SSL/TLS.

HTTP functions as the application protocol to transfer information on the web. However, it lacks security features which can expose data to potential threats. This is where SSL/TLS comes in.

SSL (Secure Sockets Layer) or TLS (Transport Layer Security), are cryptographic protocols that provide communications security over a network. They use asymmetric cryptography for authentication, symmetric encryption for confidentiality, and message authentication codes for message integrity.

When a user connects to an HTTPS-secured server, the website sends its SSL certificate to the user’s browser. This certificate contains the public key needed to start the secure session. The two systems then go through a process called an SSL handshake, which establishes a secure connection between them.

This entire process ensures that any data transferred between the user and the site is encrypted and cannot be read by anyone else, making HTTPS secure.

## Why HTTPS is Considered Secure
Encryption:

HTTPS uses strong encryption algorithms (such as AES) to encrypt the data transmitted between the client and server. This prevents eavesdroppers from reading the data as it travels across the network.
Authentication:

The server’s certificate, issued by a trusted CA, authenticates the server’s identity. This ensures that the client is communicating with the legitimate server and not an imposter (protects against man-in-the-middle attacks).
Data Integrity:

HTTPS uses cryptographic hash functions and MACs to ensure data integrity. Any alteration of data during transit can be detected, preventing tampering.
Confidentiality:

The use of symmetric session keys for encryption ensures that even if someone intercepts the encrypted data, they cannot decrypt it without the session key.
Protection against Man-in-the-Middle Attacks:

The authentication and encryption mechanisms prevent attackers from intercepting, altering, or forging messages between the client and server.
Forward Secrecy:

Many modern HTTPS implementations use a feature called forward secrecy, which ensures that session keys are not compromised even if the server’s private key is compromised in the future. This is achieved by generating unique session keys for each session that are not derived from the server’s private key.