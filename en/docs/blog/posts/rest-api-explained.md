---
title: What is a RESTful API?
date: 2025-02-25
authors: [fstueber]
slug: restful-api-erklaert
description: >
  RESTful APIs - A brief introduction
categories:
  - Standards
---

# RESTful APIs - A Brief Introduction

APIs form the foundation of modern software development. They enable communication between systems and devices – from web applications and mobile apps to IoT devices. One of the most well-known and widely used architectures for APIs is the RESTful API. But what exactly does that mean? In this article, we take a closer look at RESTful APIs, explain how they work, highlight their advantages, and provide examples.

<!-- more -->

## History of REST

The REST architecture was first described in 2000 by Roy Fielding in his dissertation [Architectural Styles and the Design of Network-based Software Architectures](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm). Fielding, one of the main authors of the HTTP specifications, aimed to define a simpler and more flexible communication method for the web compared to SOAP or other protocols.

REST quickly gained popularity, particularly with the rise of Web 2.0, as it provided an uncomplicated way to manage resources over HTTP. Major technology companies such as Twitter/X, Meta, and Google were early adopters of RESTful APIs, making their services accessible to developers. Today, RESTful APIs serve as the backbone of many web and cloud services.

## What is a RESTful API?

REST stands for *Representational State Transfer* and describes an architectural style for distributed systems, particularly web services. A RESTful API follows the principles of this architecture and enables standardised and efficient communication between a client and a server using the HTTP protocol.

A RESTful API is based on resources (data objects), which are addressed via unique [URIs (Uniform Resource Identifiers)](https://www.openpotato.org/en/blog/2024/07/18/uri-urn-url-differences/). It utilises the following HTTP methods:

+ [GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) – Retrieve data
+ [POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) – Create new data
+ [PUT](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT) or [PATCH](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH) – Update existing data
+ [DELETE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) – Delete data

## Principles of a RESTful API

An API is considered RESTful if it adheres to the following principles:

1. **Client-server architecture** - A clear separation between client and server enhances scalability.
2. **Statelessness** - Each API call contains all necessary information, eliminating the need for the server to store the client's state.
3. **Cacheability** - Responses can be cached to improve performance.
4. **Uniform interface** - Clear rules for resources and their representation facilitate usability.
5. **Layered system** - APIs can be implemented in multiple layers to enhance security and scalability.

## Advantages of RESTful APIs

REST has gained widespread adoption due to its simplicity and flexibility. Key advantages include:

+ **Platform independence** – Any client capable of sending HTTP requests can communicate with a RESTful API.
+ **Ease of understanding** – The use of standardised HTTP methods makes REST APIs intuitive.
+ **High scalability** – Stateless design and caching support scalability.
+ **Flexibility in data formats** – JSON is the most common format, but XML and others are also supported.

## Examples

### OpenHolidays API

The [OpenHolidays API](https://www.openholidaysapi.org/en/) is an Open Data project that collects public holiday and school holiday data and makes it available via an open REST API.

If you wish, you can use this API directly from your web browser. Copy the following URL into your address bar:

```
https://openholidaysapi.org/PublicHolidays?countryIsoCode=DE&validFrom=2025-01-01&validTo=2025-12-31&languageIsoCode=EN&subdivisionCode=DE-BE
```

Press Enter, and you will see the public holidays for Berlin (Germany) for the year 2025 in JSON format.

You have just interacted with a RESTful API, and it even responded to you. Not bad, right?

But what exactly happened? 

Your web browser took the URL and created an HTTP GET request, just as it always does when you enter a URL in the address bar. Usually, you receive an HTML webpage with text, images, animations, or videos. In this case, however, the HTTP GET request was sent to the web service behind the address `https://openholidaysapi.org`, which responded with JSON data instead of HTML. This is the essence of a RESTful API – communication occurs using the same technical mechanisms as when consuming websites.

Interested in more? [Here](https://openholidaysapi.org/swagger/index.html) you can explore all the API endpoints of the OpenHolidays API.

### GitHub REST API

If you want to see a fully-fledged REST API in action, the [GitHub REST API](https://docs.github.com/en/rest/quickstart) is a great example. It enables integration with GitHub services for various applications.

### Postman Public REST APIs

[Postman](https://www.postman.com/) is a popular API development tool that helps developers test, document, and automate APIs. At the [following link](https://www.postman.com/cs-demo/public-rest-apis/collection/tfzpqfc/public-rest-apis), you will find a collection of different publicly available REST APIs that you can test directly in Postman. However, you will need a (free) Postman account.

## Comparison with Other API Architectures

Although REST is widely used, other models exist:

+ [SOAP (Simple Object Access Protocol)](https://www.w3.org/TR/soap12-part1/) – An XML-based protocol offering more security features but greater complexity.
+ [GraphQL](https://graphql.org/) – Developed by Meta (formerly Facebook), providing more flexible data queries than REST.
+ [gRPC](https://grpc.io/) – A high-performance alternative from Google, leveraging [Protobufs](https://protobuf.dev/) and [HTTP/2](https://http2.github.io/).
+ [WebSockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API) – Enables real-time, bidirectional communication.

Depending on the use case, one of these alternatives may be more suitable than REST.

## Further Reading

For more information:

+ [IBM: Introduction to RESTful Web services](https://developer.ibm.com/articles/ws-restful/)
+ [Microsoft: RESTful web API design](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design)
+ [Postman: What Is a REST API? Examples, Uses, and Challenges](https://blog.postman.com/rest-api-examples/)
