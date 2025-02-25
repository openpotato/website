---
title: Was ist eine RESTful API?
date: 2025-02-25
authors: [fstueber]
slug: restful-api-erklaert
description: >
  RESTful APIs - Eine kleine Einführung
categories:
  - Standards
---

# RESTful APIs - Eine kleine Einführung

APIs sind das Fundament der modernen Softwareentwicklung. Sie ermöglichen die Kommunikation zwischen Systemen und Geräten – von Webanwendungen über Mobile Apps bis hin zu IoT-Geräten. Eine der bekanntesten und am häufigsten verwendeten Architekturen für APIs ist die RESTful API. Doch was genau bedeutet das? In diesem Artikel nehmen wir RESTful APIs unter die Lupe, erklären ihre Funktionsweise, Vorteile und zeigen Beispiele.

<!-- more -->

## Historie von REST

Die REST-Architektur wurde erstmals 2000 von Roy Fielding in seiner Dissertation [Architectural Styles and the Design of Network-based Software Architectures]((https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)) beschrieben. Fielding, einer der Hauptautoren der HTTP-Spezifikationen, wollte eine einfachere und flexiblere Methode zur Kommunikation über das Web definieren als es SOAP oder andere Protokolle boten.

REST wurde schnell populär, insbesondere mit dem Aufstieg des Web 2.0, da es eine unkomplizierte Möglichkeit bot, Ressourcen über HTTP zu verwalten. Große Technologieunternehmen wie Twitter/X, Meta und Google haben früh RESTful APIs implementiert, um ihre Dienste für Entwickler zugänglich zu machen. Heutzutage sind RESTful APIs die Basis vieler Web- und Cloud-Dienste.

## Was ist eine RESTful API?

REST steht für *Representational State Transfer* und beschreibt einen Architekturstil für verteilte Systeme, insbesondere Webservices. Eine RESTful API folgt den Prinzipien dieser Architektur und ermöglicht eine standardisierte und effiziente Kommunikation zwischen Client und Server über das HTTP-Protokoll.

Eine RESTful API basiert auf Ressourcen (Datenobjekten), die über eindeutige [URIs (Uniform Resource Identifiers)](https://www.openpotato.org/de/blog/2024/07/18/uri-urn-url-unterschiede/) adressiert werden. Dabei nutzt sie die HTTP-Methoden:

+ [GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) – Abrufen von Daten
+ [POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) – Erstellen neuer Daten
+ [PUT](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT) oder [PATCH](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH) – Aktualisieren vorhandener Daten
+ [DELETE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) – Löschen von Daten

## Prinzipien einer RESTful API

Eine API gilt als RESTful, wenn sie die folgenden Prinzipien befolgt:

1. **Client-Server-Architektur** - Eine klare Trennung zwischen Client und Server erleichtert die Skalierbarkeit.
2. **Stateless** - Jeder API-Aufruf enthält alle erforderlichen Informationen, ohne dass der Server den Zustand des Clients speichern muss.
3. **Cache-Fähigkeit** - Antworten können gecacht werden, um die Performanz zu optimieren.
4. **Einheitliche Schnittstelle (Uniform Interface)** - Klare Regeln für Ressourcen und ihre Darstellung erleichtern die Nutzung.
5. **Schichtarchitektur (Layered System)** - APIs können in mehreren Schichten implementiert werden, um Sicherheit und Skalierbarkeit zu verbessern.

## Vorteile von RESTful APIs

REST hat sich aufgrund seiner Einfachheit und Flexibilität durchgesetzt. Zu den wichtigsten Vorteilen gehören:

+ **Plattformunabhängigkeit** – Jeder Client, der HTTP-Anfragen senden kann, kann mit einer RESTful API kommunizieren.
+ **Leicht verständlich** – Die Verwendung standardisierter HTTP-Methoden macht REST-APIs intuitiv.
+ **Hohe Skalierbarkeit** – Dank Stateless-Design und Caching lassen sich RESTful APIs gut skalieren.
+ **Flexibilität bei Datenformaten** – JSON ist das beliebteste Format, aber auch XML oder andere Formate sind möglich.

## Beispiele

### OpenHolidays API

Die [OpenHolidays API](https://www.openholidaysapi.org/de/) ist ein Open Data-Projekt, das öffentliche Daten zu gesetzlichen Feiertagen und Schulferien sammelt und über eine offene REST-API-Schnittstelle verfügbar macht. 

Wenn Du möchtest, kannst Du diese API direkt von Deinem Web-Browser aus nutzen. Kopiere dazu folgende URL in die Adresszeile:

```
https://openholidaysapi.org/PublicHolidays?countryIsoCode=DE&validFrom=2025-01-01&validTo=2025-12-31&languageIsoCode=DE&subdivisionCode=DE-BE
```

Drücke OK und Du siehst die Feiertage für Berlin für das Jahr 2025 als JSON-formatierte Ausgabe. 

Hej, Du hast soeben mit einer RESTful-API gesprochen und sie hat Dir sogar geantwortet. Nicht schlecht, oder? 

Was ist da aber genau passiert? 

Nun, Dein Web-Browser hat die URL genommen und daraus eine HTTP-GET-Abfrage gebastelt, so wie er es immer macht, wenn Du eine URL in die Adresszeile eintippst. Normalerweise bekommst Du eine HTML-Website zurück mit Texten, Bildern, Animationen oder Videos. In unserem Fall wurde die HTTP-GET-Abfrage an den Webservice hinter der Adresse `https://openholidaysapi.org` gesendet. Und dieser hat mit JSON-Daten (statt mit HTML) geantwortet. Und genau das macht den Charme einer RESTful API aus. Die Kommunikation geschieht im Prinzip mit den gleichen technischen Mitteln, wie beim Konsumieren von Webseiten.

Lust auf mehr? [Hier](https://openholidaysapi.org/swagger/index.html) kannst Du alle API-Endpunkte der OpenHolidays API ausprobieren.

### GitHub-REST-API

Wenn Du mal eine richtig fette REST-API sehen möchtest, dann ist die [GitHub-REST-API](https://docs.github.com/de/rest/quickstart) ein schönes Beispiel. Sie kann verwendet werden, um eigene Anwendungen mit GitHub zu integrieren. 

### Postman Public REST APIs

[Postman](https://www.postman.com/) ist ein beliebtes API-Entwicklungstool, das Entwicklern hilft, APIs zu testen, zu dokumentieren und zu automatisieren. Unter dem [folgenden Link](https://www.postman.com/cs-demo/public-rest-apis/collection/tfzpqfc/public-rest-apis) findest Du eine Sammlung unterschiedlicher REST-APIs, die frei nutzbar sind und die Du mit Postman direkt testen kannst. Du benötigst allerdings ein (kostenloses) Postman-Konto dazu.
 
## Abgrenzung zu anderen API-Architekturen

REST ist zwar eine weit verbreitete Architektur, aber es gibt auch andere Modelle:

+ [SOAP (Simple Object Access Protocol)](https://www.w3.org/TR/soap12-part1/) – Ein XML-basiertes Protokoll mit mehr Sicherheitsfunktionen, aber auch höherer Komplexität.
+ [GraphQL](https://graphql.org/) – Entwickelt von Meta (damals noch Facebook), bietet mehr Flexibilität bei der Datenabfrage als REST.
+ [gRPC](https://grpc.io/) – Eine leistungsstarke Alternative von Google, die auf [Protobufs](https://protobuf.dev/) und [HTTP/2](https://http2.github.io/) setzt.
+ [WebSockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API) – Ermöglicht bidirektionale Kommunikation in Echtzeit.

Je nach Anwendungsfall kann eine dieser Alternativen besser geeignet sein als REST.

## Weitere Lektüre

Weitere Informationen zum Thema:

+ [IBM: Introduction to RESTful Web services](https://developer.ibm.com/articles/ws-restful/)
+ [Microsoft: RESTful web API design](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design)
+ [Postman: What Is a REST API? Examples, Uses, and Challenges](https://blog.postman.com/rest-api-examples/)
