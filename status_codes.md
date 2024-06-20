- [HTTP response status codes](#http-response-status-codes)
  - [Information responses](#information-responses)
    - [100 Continue](#100-continue)
    - [101 Switching Protocols](#101-switching-protocols)
    - [102 Processing (WebDAV)](#102-processing-webdav)
    - [103 Early Hints](#103-early-hints)
  - [Successful Response](#successful-response)
    - [200 OK](#200-ok)
    - [201 Created](#201-created)
    - [202 Accepted](#202-accepted)
    - [203 Non-Authoritative Information](#203-non-authoritative-information)
    - [204 No Content](#204-no-content)
    - [205 Reset Content](#205-reset-content)
    - [206 Partial Content](#206-partial-content)
    - [207 Multi-Status (WebDAV)](#207-multi-status-webdav)
    - [208 Already Reported (WebDAV)](#208-already-reported-webdav)
    - [226 IM Used (HTTP Delta encoding)](#226-im-used-http-delta-encoding)
  - [Redirection messages](#redirection-messages)
    - [300 Multiple Choices](#300-multiple-choices)
    - [301 Moved Permanently](#301-moved-permanently)
    - [302 Found](#302-found)
    - [303 See Other](#303-see-other)
    - [304 Not Modified](#304-not-modified)
    - [305 Use Proxy Deprecated](#305-use-proxy-deprecated)
    - [306 unused](#306-unused)
    - [307 Temporary Redirect](#307-temporary-redirect)
    - [308 Permanent Redirect](#308-permanent-redirect)
  - [Client error responses](#client-error-responses)
    - [400 Bad Request](#400-bad-request)
    - [401 Unauthorized](#401-unauthorized)
    - [402 Payment Required Experimental](#402-payment-required-experimental)
    - [403 Forbidden](#403-forbidden)
    - [404 Not Found](#404-not-found)
    - [405 Method Not Allowed](#405-method-not-allowed)
    - [406 Not Acceptable](#406-not-acceptable)
    - [407 Proxy Authentication Required](#407-proxy-authentication-required)
    - [408 Request Timeout](#408-request-timeout)
    - [409 Conflict](#409-conflict)
    - [410 Gone](#410-gone)
    - [411 Length Required](#411-length-required)
    - [412 Precondition Failed](#412-precondition-failed)
    - [413 Payload Too Large](#413-payload-too-large)
    - [414 URI Too Long](#414-uri-too-long)
    - [415 Unsupported Media Type](#415-unsupported-media-type)
    - [416 Range Not Satisfiable](#416-range-not-satisfiable)
    - [417 Expectation Failed](#417-expectation-failed)
    - [418 I'm a teapot](#418-im-a-teapot)
    - [421 Misdirected Request](#421-misdirected-request)
    - [422 Unprocessable Content (WebDAV)](#422-unprocessable-content-webdav)
    - [423 Locked (WebDAV)](#423-locked-webdav)
    - [424 Failed Dependency (WebDAV)](#424-failed-dependency-webdav)
    - [425 Too Early Experimental](#425-too-early-experimental)
    - [426 Upgrade Required](#426-upgrade-required)
    - [428 Precondition Required](#428-precondition-required)
    - [429 Too Many Requests](#429-too-many-requests)
    - [431 Request Header Fields Too Large](#431-request-header-fields-too-large)
    - [451 Unavailable For Legal Reasons](#451-unavailable-for-legal-reasons)
  - [Server error responses](#server-error-responses)
    - [500 Internal Server Error](#500-internal-server-error)
    - [501 Not Implemented](#501-not-implemented)
    - [502 Bad Gateway](#502-bad-gateway)
    - [503 Service Unavailable](#503-service-unavailable)
    - [504 Gateway Timeout](#504-gateway-timeout)
    - [505 HTTP Version Not Supported](#505-http-version-not-supported)
    - [506 Variant Also Negotiates](#506-variant-also-negotiates)
    - [507 Insufficient Storage (WebDAV)](#507-insufficient-storage-webdav)
    - [508 Loop Detected (WebDAV)](#508-loop-detected-webdav)
    - [510 Not Extended](#510-not-extended)
    - [511 Network Authentication Required](#511-network-authentication-required)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# HTTP response status codes

HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:

1. Informational responses
2. Successful responses
3. Redirection messages
4. Client error responses
5. Server error responses

## Information responses

### 100 Continue

This interim response indicates that the server has received the initial part of the request and the client can continue sending the rest of the request. It's like a green light indicating the request can proceed.

### 101 Switching Protocols

This means the server is changing to a different protocol that the client has requested. It's like agreeing to switch from talking on the phone to chatting via text message.

### 102 Processing (WebDAV)

This means the server has received the request and is working on it, but it will take some time to complete. It's like saying, "I'm working on it, please wait."

### 103 Early Hints

This means the server is sending some preliminary response headers to the client, indicating that the final response is on its way. It's like giving a sneak peek before the main event.

## Successful Response

### 200 OK

The request succeeded. The result meaning of "success" depends on the HTTP method:

- GET: The resource has been fetched and transmitted in the message body.
- HEAD: The representation headers are included in the response without any message body.
- PUT or POST: The resource describing the result of the action is transmitted in the message body.
- TRACE: The message body contains the request message as received by the server.

### 201 Created

This means the request was successful and a new resource has been created as a result. The server will include a link to the new resource in the response. It's like saying, "Your request was successful, and something new has been made!"

### 202 Accepted

This means the request has been received and accepted for processing, but the processing is not yet complete. It's like saying, "We got your request and will work on it, but it's not finished yet."

### 203 Non-Authoritative Information

This means the request was successful, but the information in the response comes from a source other than the original server. It's like saying, "Here is the data you asked for, but it's been provided by someone else."

### 204 No Content

This means the server has successfully processed the request, but there is no content to return in the response body. It's like saying, "Everything went well, but there's nothing more to show you right now."

### 205 Reset Content

This status code indicates that the server has fulfilled the request and wants the client to reset the document view, which may require the user to clear the form's input data. It's not widely used but it's meant to signal browsers to clear form data after a submission.

### 206 Partial Content

This status code indicates that the server is delivering only part of the resource because the client requested a specific range of the resource using the 'Range' header in the request. It's like saying, "Here's the part of the content you asked for." This is often used for resuming interrupted downloads or streaming large files.

### 207 Multi-Status (WebDAV)

This status code is used in Web Distributed Authoring and Versioning (WebDAV) protocols to indicate multiple status codes for multiple independent operations within a single request. It's like saying, "Here are the results of several different actions you requested, each with its own status."

### 208 Already Reported (WebDAV)

This status code is used in the Web Distributed Authoring and Versioning (WebDAV) protocol to indicate that the members of a DAV binding have already been enumerated in a previous part of the multistatus response, and are not being included again. It's like saying, "You've already received this information in an earlier response, so I'm not repeating it here."

### 226 IM Used (HTTP Delta encoding)

This status code indicates that the server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance. It's used in the context of HTTP delta encoding, which is a method for efficiently transmitting changes to a resource. This status tells the client that the response uses instance-manipulation (IM) techniques to provide the requested content.

## Redirection messages

### 300 Multiple Choices

This status code indicates that the requested resource has multiple representations available, each with potentially different locations (URIs), and the user or user agent can choose among them. It's like saying, "Here are several options for what you requested; please choose one." This can be used for content negotiation scenarios where the server offers different versions or formats of the same resource.

### 301 Moved Permanently

This status code indicates that the requested resource has been permanently moved to a new URL. The client should use the new URL for all future requests. It's like saying, "The resource you are looking for has moved permanently to a new location."

### 302 Found

This status code indicates that the requested resource temporarily resides under a different URL. The client should continue to use the original URL for future requests, as the redirection might be temporary. It's like saying, "The resource you are looking for is temporarily located elsewhere."

### 303 See Other

This status code indicates that the response to the request can be found under a different URI and should be retrieved using a GET method on that URI. It's often used to redirect a client to a different resource after performing a POST request, preventing the client from resubmitting the same data if they refresh the page. It's like saying, "You can find what you're looking for at this other location; go there with a GET request."

### 304 Not Modified

This status code indicates that the client's cached copy of the resource is still valid and can be used. The server sends this response when the client's conditional request (using If-Modified-Since or If-None-Match headers) indicates that the resource has not been modified since the last request. It's like saying, "Your cached version is up-to-date; no need to fetch it again."

### 305 Use Proxy Deprecated

This status code was used in earlier versions of the HTTP protocol (HTTP/1.1) to inform the client that it must use the specified proxy server to access the requested resource. However, it has been deprecated and is no longer used in practice. Servers and clients should not rely on it.

### 306 unused

This status code was proposed in the HTTP/1.1 specification but was never standardized or implemented in practice. It was intended for use as a reserved code for future purposes, but it remains unused and is not supported by HTTP servers or clients.

### 307 Temporary Redirect

This status code indicates that the requested resource is temporarily located at a different URL. The client should continue to use the original URL for future requests, as the redirection is temporary and the request method (such as POST or PUT) should not be changed. It's like saying, "The resource you are looking for is temporarily available at a different location; use the original URL for subsequent requests."

### 308 Permanent Redirect

This status code indicates that the requested resource has been permanently moved to a different URL. Similar to a 301 status code, the client should use the new URL for all future requests. However, unlike a 301, the request method (such as POST or PUT) should not be changed. It's like saying, "The resource you are looking for has permanently moved to a new location; use the new URL for future requests without changing the request method."

## Client error responses

### 400 Bad Request

This status code indicates that the server cannot process the client's request due to malformed syntax or a client error. It's like saying, "I can't understand what you're asking for because there's something wrong with the request itself."

### 401 Unauthorized

This status code indicates that the request lacks valid authentication credentials or the authentication credentials provided are not sufficient. In simpler terms, it means, "You are not authorized to access this resource. Please provide valid credentials."

### 402 Payment Required Experimental

This status code was reserved for future use and intended to indicate that payment is required for the requested resource. However, it was never widely implemented and remains unused in practice.

### 403 Forbidden

This status code indicates that the server understood the request, but it refuses to authorize it. This often happens when the server recognizes the client's identity and credentials, but the client does not have sufficient permissions to access the requested resource. It's like saying, "You are not allowed to access this resource. Access is forbidden."

### 404 Not Found

This status code indicates that the server cannot find the requested resource. It's like saying, "The resource you are looking for is not available on this server."

### 405 Method Not Allowed

This status code indicates that the HTTP method (GET, POST, PUT, DELETE, etc.) used in the request is not allowed for the specified resource. It's like saying, "You can't use that method with this resource."

### 406 Not Acceptable

This status code indicates that the server cannot generate a response that is acceptable according to the Accept headers sent in the request. It's like saying, "I can't provide a response in a format that meets your requirements." This might happen if the client specifies certain content types or character sets that the server cannot provide.

### 407 Proxy Authentication Required

This status code indicates that the client needs to authenticate itself with the proxy server before it can access the requested resource. It's like saying, "You need to provide authentication credentials to the proxy server in order to access this resource."

### 408 Request Timeout

This status code indicates that the client did not produce a request within the time that the server was prepared to wait. It's like saying, "I waited too long for your request, so I'm giving up." This can happen due to network issues, server overload, or client-side timeouts.

### 409 Conflict

This status code indicates that the request could not be completed due to a conflict with the current state of the resource. It's like saying, "There's a conflict with what you're trying to do because of the current state of the resource." This typically occurs when there are conflicting edits or modifications being made to the same resource simultaneously.

### 410 Gone

This status code indicates that the requested resource is no longer available and has been intentionally removed. It's like saying, "The resource you are looking for used to be here, but it's gone now and won't be coming back."

### 411 Length Required

This status code indicates that the server refuses to accept the request without a defined Content-Length header. It's like saying, "I need to know the length of the content you're sending in the request, but you didn't provide that information." This typically occurs with POST or PUT requests where the server needs to know the size of the message body.

### 412 Precondition Failed

This status code indicates that one or more preconditions specified in the request headers evaluated to false when tested on the server. It's like saying, "The conditions you specified for this request were not met." This can happen with conditional requests using headers like If-Match, If-None-Match, If-Modified-Since, or If-Unmodified-Since, where the server checks if certain conditions are true before proceeding with the request.

### 413 Payload Too Large

This status code indicates that the server refused to process the request because the request payload (body) is larger than the server is willing or able to process. It's like saying, "The data you're trying to send is too big for me to handle."

### 414 URI Too Long

This status code indicates that the URI (Uniform Resource Identifier) provided in the request is too long for the server to process. It's like saying, "The URL you provided is too lengthy for me to handle." Servers typically have limits on the length of URIs they can process, and this status code informs the client to shorten the URI for the request to be successful.

### 415 Unsupported Media Type

This status code indicates that the server refuses to accept the request because the payload (body) format is in an unsupported media type. It's like saying, "I cannot process the content in the format you provided." This typically occurs when the server cannot handle the media type specified in the Content-Type header of the request.

### 416 Range Not Satisfiable

: This status code indicates that the client has requested a portion of the resource using the Range header, but the server cannot satisfy the range request. It's like saying, "I cannot provide the specific range of data you requested." This can happen if the range specified is outside the current size of the resource or if the range is invalid.

### 417 Expectation Failed

This status code indicates that the server cannot meet the expectations indicated by the Expect request header field. This typically happens when the server is unable to fulfill the requirements specified in the Expect header sent by the client, such as certain content characteristics or behaviors. It's like saying, "I cannot meet the expectations you specified in your request."

### 418 I'm a teapot

This status code is defined in the HTTP protocol as an April Fools' joke and is not intended to be implemented seriously. It was specified in RFC 2324 (Hyper Text Coffee Pot Control Protocol) as an April Fools' Day joke in 1998. Servers are not expected to implement this status code, and it's used humorously to indicate that the server is a teapot, not capable of handling the request.

### 421 Misdirected Request

This status code indicates that the request was directed at a server that is not able to produce a response. This typically occurs when the client connects to a server and expects a response, but the server identifies that the request should actually be sent to another server or endpoint. It's like saying, "You've sent your request to the wrong place; it needs to go somewhere else."

### 422 Unprocessable Content (WebDAV)

This status code is used in the Web Distributed Authoring and Versioning (WebDAV) protocol to indicate that the server understands the content type of the request entity, and the syntax of the request entity is correct, but it was unable to process the contained instructions. It's like saying, "I understand what you sent me, but I can't do what you're asking with it." This could be due to semantic errors, validation errors, or other issues specific to the request entity.

### 423 Locked (WebDAV)

This status code is used in the Web Distributed Authoring and Versioning (WebDAV) protocol to indicate that the resource that is being accessed is locked. It's like saying, "The resource you're trying to access is currently locked by another process or user." This typically occurs in collaborative environments where resources are locked to prevent conflicting updates.

### 424 Failed Dependency (WebDAV)

This status code is used in the Web Distributed Authoring and Versioning (WebDAV) protocol to indicate that the method could not be performed on the resource because the requested action depends on another resource's state. It's like saying, "The request failed because it relied on another operation that did not succeed." This can happen when a previous request failed to modify the state of a related resource, preventing the current request from being successful.

### 425 Too Early Experimental

This status code indicates that the server is unwilling to risk processing a request that might be replayed. It suggests that the client should wait and then try the request again later. However, this status code is experimental and not widely implemented in practice.

### 426 Upgrade Required

This status code indicates that the server refuses to perform the request using the current protocol but might be willing to do so after the client upgrades to a different protocol. It's like saying, "You need to switch to a different protocol to make this request." This typically happens when the server requires the client to upgrade to a newer version of the protocol to continue communication.

### 428 Precondition Required

This status code indicates that the server requires the client to include specific conditional headers (such as If-Match, If-None-Match, If-Modified-Since, etc.) in the request headers. It's like saying, "You need to include certain conditions in your request for me to process it." This is often used to prevent the "lost update" problem in concurrent modifications of resources.

### 429 Too Many Requests

This status code indicates that the client has sent too many requests in a given amount of time ("rate limiting"). It's like saying, "You're requesting too frequently; slow down." This status is used to prevent abuse and overload of the server by limiting the rate at which the client can make requests.

### 431 Request Header Fields Too Large

This status code indicates that the server is refusing to process the request because the request headers are too large. It's like saying, "The headers you sent are too big for me to handle." This typically happens when the size of the request headers exceeds server limitations or configurations.

### 451 Unavailable For Legal Reasons

This status code indicates that the server is denying access to the resource as a consequence of legal demands. It's like saying, "Access to this resource is not available due to legal reasons." This status is typically used when content is blocked due to legal issues such as censorship, court orders, or government restrictions.

## Server error responses

### 500 Internal Server Error

This status code indicates that the server encountered an unexpected condition that prevented it from fulfilling the request. It's like saying, "Something went wrong on the server's end, but it's not your fault." This error can occur due to various reasons such as bugs in the server-side application, configuration issues, or unexpected server downtime.

### 501 Not Implemented

This status code indicates that the server does not support the functionality required to fulfill the request. It's like saying, "I don't know how to handle this type of request." This typically occurs when the server does not recognize the request method (GET, POST, etc.) or does not support the functionality required to process the request.

### 502 Bad Gateway

This status code indicates that the server, while acting as a gateway or proxy, received an invalid response from an inbound server it accessed to fulfill the request. In simpler terms, it means, "I received an invalid response from another server that I tried to access to complete your request." This often happens when there are connectivity issues or problems with the upstream server that the gateway or proxy is trying to communicate with.

### 503 Service Unavailable

This status code indicates that the server is currently unable to handle the request due to temporary overload or maintenance of the server. It's like saying, "I'm currently unavailable to process your request; please try again later." This status code is commonly used when a server is undergoing maintenance, experiencing temporary overload, or is temporarily unable to handle requests for other reasons.

### 504 Gateway Timeout

This status code indicates that the server, acting as a gateway or proxy, did not receive a timely response from an upstream server it needed to access in order to complete the request. It's like saying, "I tried to communicate with another server to complete your request, but it didn't respond in time." This typically happens when the upstream server is slow to respond or is experiencing issues.

### 505 HTTP Version Not Supported

This status code indicates that the server does not support the HTTP protocol version used in the request. It's like saying, "I can't understand the version of HTTP that you're using." This typically occurs when the client sends a request with an HTTP version that the server does not recognize or support.

### 506 Variant Also Negotiates

This status code indicates that the server has an internal configuration error. It occurs when it encounters an inconsistent negotiation algorithm, thus failing to select a representation that the client can understand.

### 507 Insufficient Storage (WebDAV)

This status code is used in the Web Distributed Authoring and Versioning (WebDAV) protocol to indicate that the server is unable to store the representation needed to complete the request. It's like saying, "I don't have enough storage space to fulfill your request." This typically happens when the server runs out of space while trying to store data related to the request.

### 508 Loop Detected (WebDAV)

This status code is used in the Web Distributed Authoring and Versioning (WebDAV) protocol to indicate that the server detected an infinite loop while processing a request. It's like saying, "There's a loop in the processing of your request that I cannot resolve." This typically happens when there's a recursive chain of requests or operations that leads to an infinite loop situation on the server.

### 510 Not Extended

This status code indicates that the client needs to extend its request further for the server to proceed with it. It's like saying, "Your request is missing some required extensions." This status code is not commonly used and is typically reserved for future use or experimental purposes.

### 511 Network Authentication Required

This status code indicates that the client needs to authenticate to gain network access. It's typically used when a server requires the client to authenticate using some form of network authentication, such as HTTP authentication or captive portal authentication, before granting access to the network or resource.
