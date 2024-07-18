---
title: URI, URL, URN - Was ist der Unterschied?
date: 2024-07-18
authors: [fstueber]
slug: uri-urn-url-unterschiede
description: >
  Erläuterung der grundlegenden Konzepte von URI, URN und URL. 
categories:
  - Web
---

# URI, URL, URN - Was ist der Unterschied?

Die Konzepte URI, URN und URL sind von grundlegender Bedeutung für die Internetkommunikation und cloudbasierte Technologien.  Sie klingen ähnlich, fast gleich und doch hat jedes Akronym seine eigene Bedeutung. In diesem Blog-Artikel werden die Unterschiede zwischen den Begriffen erläutert.

<!-- more -->

## URI (Uniform Resource Identifier)

Eine [URI](https://datatracker.ietf.org/doc/html/rfc3986) ist eine Zeichenkette, die verwendet wird, um eine Ressource im Internet zu identifizieren. Es handelt sich hierbei um einen umfassenden Begriff, der sowohl URLs als auch URNs einschließt. Es gibt zwei Haupttypen von URIs:

+ **URL (Uniform Resource Locator)**: Gibt den Standort einer Ressource an.
+ **URN (Uniform Resource Name)**: Gibt den Namen einer Ressource an, ohne ihren Standort zu implizieren.

Im Wesentlichen kann eine URI entweder eine URL, eine URN oder beides sein. Der wichtigste Aspekt einer URI ist, dass er als allgemeiner Bezeichner für eine Ressource dient.

## URL (Uniform Resource Locator)

Eine URL ist ein Typ von URI, der beschreibt, wie eine Ressource im Netzwerk gefunden werden kann. Sie enthält Informationen wie das zu verwendende Protokoll (z.B. HTTP, FTP), den Hostnamen (z.B. www.beispiel.de) und manchmal einen Pfad oder eine Abfragezeichenfolge, um die spezifische Ressource zu identifizieren.

Beispiel für eine URL:

```
http://www.beispiel.de/index.html
```

Hier:

+ `http` ist das Protokoll.
+ `www.beispiel.de` ist der Hostname.
+ `/index.html` ist der Pfad zur spezifischen Ressource.

## URN (Uniform Resource Name)

Eine URN ist ein Typ von URI, der eine eindeutige und dauerhafte Kennung für eine Ressource bereitstellt, ohne ihren Standort oder den Zugriffsweg zu beschreiben. URNs sollen als dauerhafte, standortunabhängige Ressourcenkennung dienen.

Beispiel für eine URN:

```
urn:isbn:978-3-16-148410-0
```

Hier:

+ `urn` zeigt an, dass es sich um eine URN handelt.
+ `isbn` ist der Namespace-Identifier.
+ `978-3-96111-268-5` ist der spezifische Ressourcename innerhalb des `isbn` Namespace.

## Hauptunterschiede

+ **Geltungsbereich**: URI ist ein umfassender Begriff, der sowohl URLs als auch URNs einschließt.

+ **Zweck**:
    - URL: Wird verwendet, um den Standort einer Ressource anzugeben.
    - URN: Wird verwendet, um eine Ressource eindeutig zu benennen.

+ **Struktur**:
    - URL: Enthält Informationen darüber, wie auf eine Ressource zugegriffen werden kann (Protokoll, Hostname, Pfad).
    - URN: Enthält einen eindeutigen Namen innerhalb eines Namespace, ohne Standortinformationen.

## Beispiele im Kontext

Eine URI kann entweder eine URL oder eine URN sein.

+ `http://www.beispiel.de` (URL und URI)
+ `urn:isbn:978-3-96111-268-5` (URN und URI)
