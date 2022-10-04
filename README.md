# TCP, HTTP, and Websocket

## Learning Goals

- Create websocket connections between clients and servers to improve our
  applications' performance.

***

## Key Vocab

- **Full-Stack Development**: development of a frontend and a backend for an
  application. True full-stack development includes a database, a logic/server
  layer, and a frontend built in JavaScript, HTML, and CSS.
- **Backend**: the layer of a full-stack application that handles business logic
  and other programmatic tasks that users do not or should not see. Can be
  written in many languages, including Python, Java, Ruby, PHP, and more.
- **Frontend**: the layer of a full-stack application that users see and
  interact with. It is always written in the frontend languages: JavaScript,
  HTML, and CSS. (_There are others now, but they are based on these three._)
- **Cross-Origin Resource Sharing (CORS)**: a method for a server to indicate
  any ports (or other identifiers) for servers that can share its resources.
- **Transmission Control Protocol (TCP)**: a protocol that defines how computers
  send data to each other. A connection is formed and stars active until the
  applications on either end have finished sending data to one another.
- **Hypertext Transfer Protocol (HTTP)**: a stateless protocol where
  applications communicate for the length of time that it takes for data to be
  transferred.
- **WebSocket**: a protocol that allows clients and servers to communicate with
  one another in both directions. The bidirectional nature of websocket
  communication allows a connected state to be generated and the connection
  maintained until it is terminated by one side. This allows for speedy and
  seamless connections between frontends and backends.

***

## Introduction

Through this whole unit, we have seen information transmitted from servers to
clients. We have only done this fairly short-distance, but with Procfiles and
deployment platforms such as Render and Heroku, we can use the same code to
communicate across the globe through the internet.

Communication between so many internet-connected devices across such a wide area
requires a certain set of standards. All internet communication relies on the
Internet Protocol (IP) and Transmission Control Protocol (TCP). IP dictates how
messages are sent between networks on the internet. It is upheld by all
internet-based applications.

Where IP is focused on messages, TCP is focused on connections. It is a stateful
protocol, meaning that it remembers previous transactions for the duration of
the connection. This statefulness makes TCP _reliable_: it knows what works and
what doesn't based on its history. It also makes TCP _kind of slow_.

While TCP is imperfect, it makes for a great base for faster and more specific
protocols. In this lesson, we're going to dive deeper into two of those: HTTP
and Websocket.

***

## Hypertext Transfer Protocol (HTTP)

Hypertext Transfer Protocol, or HTTP, is built atop TCP and allows users and
applications to communicate via hypertext (e.g. HTML). Most internet users have
likely noticed that HTTP is the most popular means of accessing internet
resources by far. It adheres to a client-server model, where the client is
typically a web browser and the server is...well, a server! Every web
application has one, after all.

In HTTP, the client opens a connection to make a request, then waits for a
response from the server. The connection ends when the response is received
and the server does not keep any data while waiting for a new request. This
means that HTTP is stateless- even though it's built on top of TCP, a stateful
protocol! Because HTTP is stateless, it is faster than traditional TCP.

HTTP requests are typically sent over port 80. If you see a URL without a
specified port in your browser, it might be running on port 80. If you see
a lock to the left of the domain name, however, you're running on port 443
for HTTPS.

### HTTPS

Hypertext Transfer Protocol Secure (HTTPS) uses encryption to ensure secure
communications between the client and server. The protocol used for encryption
is called Transport Layer Security (TLS) and secures communications with a
public key and a private key.

- A **public key** is available to anyone who wanted to interact with a server
  over HTTPS. The public key is used to encrypt a website's data.
- A **private key** is only available to the owner of a website. It lives on the
  server and decrypts information that has been encrypted by the public key.

All communication over HTTP uses easily-readable plain text, which does not
leave your data very secure on its own. Encryption ensures that others in your
network cannot see the plain text that you're sending and receiving when using
the internet.

### Downsides to HTTP

While being stateless allows HTTP to convey messages more quickly than TCP, it
requires the client to either request all of the data it wants at once or make
a number of new requests. If a client needs updates from the server in real
time, HTTP is no longer quite as appealing a solution.

The work-around to this- HTTP long-polling- allowed servers to maintain an HTTP
connection for a long period, which gave the client more time to receive data
that aligned with a certain request. This unfortunately requires quite a bit of
work for the server, and there's no guarantee that new data will come during a
polling session.

Full-stack applications often desire fast, real-time updates between the
client and server. Updates to HTTP have improved its ability to serve as a
client-server intermediary in this context, but it's still far from perfect. To
improve communication in a full-stack context, a team of engineers designed
a new protocol: **WebSocket**.

***

## WebSocket

Like HTTP, WebSocket is built on top of an existing TCP connection. Unlike HTTP,
the connection is bidirectional and stateful: the client and server remain
connected and can communicate with each other freely without establishing new
connections.

WebSocket starts as an HTTP request: the client sends a request to the server,
though this request is to open a WebSocket connection. If this request is
successful, the TCP connection between client and server is reinterpreted as a
WebSocket connection. Data can continue traveling back and forth until one side
terminates the connection.

***

## Conclusion

TCP, HTTP, and WebSocket are connection protocols that you need to know to be an
effective web application developer. We've done a good amount of HTTP work so
far (especially in our **REST APIs** module)- in the next bonus lesson, we'll
dig deeper into WebSocket with [Socket.IO](https://socket.io/).

***

## Resources

- [What are IP & TCP? - CloudFlare](https://www.cloudflare.com/learning/ddos/glossary/tcp-ip/)
- [HTTP - Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP)
- [The WebSocket API (WebSockets) - Mozilla](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
