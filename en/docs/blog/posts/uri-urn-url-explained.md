---
title: URI, URL, URN - What's the difference?
date: 2024-07-18
authors: [fstueber]
slug: uri-urn-url-explained
description: >
  Explanation of the basic concepts of URI, URN and URL. 
categories:
  - Web
---

# URI, URL, URN - What's the difference?

The concepts of URI, URN, and URL are fundamental in the realm of web development and internet communication. They sound similar, almost the same and yet each acronym has its own meaning. This blog article is a breakdown of their differences.

<!-- more -->

## URI (Uniform Resource Identifier)

A [URI](https://datatracker.ietf.org/doc/html/rfc3986) is a string of characters used to identify a resource on the internet. It is a broader concept that encompasses both URLs and URNs. There are two main types of URIs:

+ **URL (Uniform Resource Locator)**: Specifies the location of a resource.

+ **URN (Uniform Resource Name)**: Specifies the name of a resource without implying its location.

In essence, a URI can be either a URL, a URN, or both. The key aspect of a URI is that it serves as a generic identifier for a resource.

## URL (Uniform Resource Locator)

A URL is a type of URI that specifies the means of locating a resource on a network. It includes information such as the protocol to use (e.g., HTTP, FTP), the hostname (e.g., www.example.com), and sometimes a path or query string to identify the specific resource.

**Example of a URL:**

```
http://www.example.com/index.html
```

Here:

+ `http` is the protocol.
+ `www.example.com` is the hostname.
+ `/index.html` is the path to the specific resource.

### URN (Uniform Resource Name)

A URN is a type of URI that provides a unique and persistent identifier for a resource, without describing its location or how to access it. URNs are intended to serve as persistent, location-independent resource identifiers.

**Example of a URN:**

```
urn:isbn:978-3-96111-268-5
```

Here:

+ `urn` indicates that it is a URN.
+ `isbn` is the namespace identifier.
+ `978-3-16-148410-0` is the specific resource name within the `isbn` namespace.

### Key Differences

+ **Scope**: URI is a broad concept that includes both URLs and URNs.

+ **Purpose**:
    - URL: Used to locate a resource.
    - URN: Used to name a resource uniquely.

+ **Structure**:
    - URL: Contains information about how to access a resource (protocol, hostname, path).
    - URN: Contains a unique name within a namespace, without location information.
