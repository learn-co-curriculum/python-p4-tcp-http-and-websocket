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
- **Websocket**: a protocol that allows clients and servers to communicate with
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

***

## Resources

- [What are IP & TCP? - CloudFlare](https://www.cloudflare.com/learning/ddos/glossary/tcp-ip/)
- [HTTP - Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP)
- [The WebSocket API (WebSockets) - Mozilla](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
