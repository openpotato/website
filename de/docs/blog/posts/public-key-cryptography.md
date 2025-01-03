---
title: Public-Key-Kryptographie
date: 2025-01-03
authors: [fstueber, chatgtp]
slug: public-key-kryptographie
description: >
  Eine kurze Einführung in die Public-Key-Kryptographie
categories:
  - InfoSec
---

# Public-Key-Kryptographie

Stell Dir vor, Du möchtest eine geheime Nachnricht mit einem Freund teilen, ohne dass jemand anderes mitlesen kann. Das Problem dabei: Ihr befindet euch auf entgegengesetzten Seiten der Welt, und ihr vertraut dem Postboten nicht. Genau das ermöglicht die Public-Key-Kryptographie – eine Methode, um Geheimnisse sicher zu teilen, selbst wenn die ganze Welt zuschaut.

<!-- more -->

## Ein Blick zurück

Früher nutzte man **symmetrische Verschlüsselung**, bei der ein einziger Schlüssel verwendet wurde. Also: Du steckst Deine Nachricht in eine Box und verschließt sie. Dein Freund benötigt denselben Schlüssel, um sie wieder zu öffnen. Das Problem dabei ist jedoch: Wie teilt man den Schlüssel? Wenn Du ihn ebenfalls versendest und jemand bekommt ihn in die Hände, ist Deine Nachricht nicht mehr sicher.

In den 1970er Jahren revolutionierte eine Gruppe von Mathematikern — *Whitfield Diffie, Martin Hellman* und später *Rivest, Shamir und Adleman (RSA)* — die Kryptographie. Sie führten die Idee ein, *zwei* Schlüssel zu verwenden: einen öffentlichen und einen privaten. Damit wurde sichere Kommunikation selbst bei öffentlichem Schlüsselaustausch möglich.

## Wie funktioniert das?

Die Public-Key-Kryptographie basiert auf zwei Schlüsseln:

+ **Der öffentliche Schlüssel**: Dieser wird mit allen geteilt. Es ist, als ob man einen Briefkasten vor sein Haus stellt, in den jeder Briefe einwerfen kann.
+ **Der private Schlüssel**: Dieser bleibt geheim. Nur mit diesem Schlüssel kann der Briefkasten geöffnet werden.

So können Alice und Bob sicher kommunizieren:

1. Bob erstellt ein Schlüsselpaar – einen öffentlichen und einen privaten Schlüssel - und sendet den öffentlichen Schlüssel an Alice. 
2. Alice verschlüsselt ihre Nachricht an Bob mit seinem öffentlichen Schlüssel.
3. Alice verschickt die verschlüsselte Nachricht an Bob.
4. Bobs entschlüsselt die Nachricht mit seinem privaten Schlüssel und kann diese dann lesen.

[![Infografik Public-Key-Kryptographie][1]][1]

## Die mathematischen Grundlagen

Im Kern der Public-Key-Kryptographie stehen **Einwegfunktionen** – mathematische Operationen, die leicht in eine Richtung auszuführen, aber extrem schwer rückgängig zu machen sind. Zum Beispiel ist es einfach, eine Vase zu zerbrechen, aber fast unmöglich, sie wieder zusammenzusetzen.

Die Public-Key-Kryptographie nutzt Einwegfunktionen, um:

+ Daten mit dem öffentlichen Schlüssel zu verschlüsseln.
+ Daten mit dem privaten Schlüssel zu entschlüsseln, indem der "schwierige Teil" der Mathematik gelöst wird.

### RSA-Verschlüsselung

Der bekannteste Algorithmus für Public-Key-Kryptographie, **RSA**, basiert auf **Primfaktorzerlegung** und **modularer Arithmetik**. Die Primfaktorzerlegung macht es einfach, zwei große Primzahlen zu multiplizieren, aber sehr schwer, das Produkt wieder in die Faktoren zu zerlegen. Die modulare Arithmetik, ähnlich einer Uhr, die nach 12 zurücksetzt, stellt sicher, dass Berechnungen nicht leicht rückgängig gemacht werden können.

**Wie RSA funktioniert**:

1. Wähle zwei große Primzahlen \( p \) und \( q \) und berechne \( n = p \times q \).
2. Berechne \( \phi(n) = (p - 1)(q - 1) \), was zur Berechnung des privaten Schlüssels dient. 
3. Wähle \( e \), eine Zahl, die zu \( \phi(n) \) teilerfremd ist, und bilde den öffentlichen Schlüssel.
4. Berechne \( d \), den privaten Schlüssel, sodass:
   $$
   (e \cdot d) \mod \phi(n) = 1
   $$

Um eine Nachricht \( M \) zu verschlüsseln:  
$$
C = M^e \mod n
$$

Um sie zu entschlüsseln:  
$$
M = C^d \mod n
$$

**Beispiel** (mit kleinen Zahlen):  

+ Wähle \( p = 7 \), \( q = 11 \). Dann \( n = 77 \) und \( \phi(n) = 60 \). 
+ Wähle \( e = 17 \) (teilerfremd zu 60). Berechne \( d = 53 \).  
+ Öffentlicher Schlüssel: \( (77, 17) \), Privater Schlüssel: \( 53 \).  

Verschlüsseln mit \( M = 10 \):  
$$
C = 10^{17} \mod 77 = 17
$$

Entschlüsseln mit \( C = 17 \):  
$$
M = 17^{53} \mod 77 = 10
$$

Wer ein wenig mit RSA "rumspielen" möchte, der kann das mit einem [interaktivem Playground](https://www.ntietz.com/demos/bleichenbacher/) probieren.

### Elliptic Curve Cryptography (ECC)

Während RSA leistungsstark ist, stellt die **Elliptische-Kurven-Kryptographie (ECC)** eine effizientere Alternative dar. Statt auf Primfaktorzerlegung basiert ECC auf den Eigenschaften von Punkten auf einer Kurve, um mit kleineren Schlüsseln und weniger Rechenaufwand die gleiche Sicherheit zu erreichen.

### Anmerkung

Public-Key-Kryptographie ist in der Regel langsamer als symmetrische Verschlüsselung. Daher verwenden die meisten Systeme einen hybriden Ansatz: Public-Key-Kryptographie, um einen symmetrischen Schlüssel sicher auszutauschen, der dann die eigentlichen Daten schnell verschlüsselt.

## Anwendungen

Schauen wir auf einige reale Technologien, bei denen Public-Key-Kryptographie eine entscheidende Rolle spielt.

### Transport Layer Security (TLS)

TLS ist das Protokoll, das dafür sorgt, dass Verbindungen zwischen einem Web-Browser und einer Webseite sicher sind. Du kennst es von dem kleinen Schloss-Symbol in deinem Web-Browser oder dem `https://` in der Adresszeile.

Wie wird Public-Key-Kryptographie verwendet?

+ Beim Aufbau einer HTTPS-Verbindung wird Public-Key-Kryptographie verwendet, um die sichere Übertragung eines **symmetrischen Schlüssels** zu ermöglichen. Dieser Schlüssel wird dann für die Verschlüsselung der weiteren Kommunikation verwendet.

+ Ein Server besitzt ein **Zertifikat** mit einem öffentlichen Schlüssel. Der Browser verwendet diesen Schlüssel, um mit dem Server sicher zu kommunizieren und die Identität des Servers zu prüfen.

### Digitale Signaturen

Digitale Signaturen sind die digitale Entsprechung von handschriftlichen Unterschriften, aber wesentlich sicherer. Sie gewährleisten:

+ **Authentizität**: Die Nachricht stammt wirklich vom Absender.
+ **Integrität**: Die Nachricht wurde nicht manipuliert.
+ **Nichtabstreitbarkeit**: Der Absender kann nicht leugnen, die Nachricht gesendet zu haben.

Wie funktioniert das mit Public-Key-Kryptographie?

+ Der Absender erzeugt mit seinem privaten Schlüssel eine Signatur für eine Nachricht oder ein Dokument.
+ Der Empfänger überprüft die Signatur mit dem öffentlichen Schlüssel des Absenders.

Beispiele:

+ Signieren von Verträgen oder PDFs.
+ Sicherstellen der Integrität von Software-Updates.

### Verschlüsselung und Signatur von E-Mails

E-Mails können verschlüsselt und signiert werden. Das hat folgende Vorteile:

+ **Vertraulichkeit**: Es wird sichergestellt, dass nur der beabsichtigte Empfänger die E-Mail lesen kann .
+ **Authentizität**: Es wird garantieren, dass die E-Mail wirklich vom Absender stammt.

Wie wird Public-Key-Kryptographie eingesetzt?

+ **Verschlüsselung**: Der Absender verwendet den öffentlichen Schlüssel des Empfängers, um die Nachricht zu verschlüsseln. Der Empfänger entschlüsselt sie mit seinem privaten Schlüssel.
+ **Signatur**: Der Absender signiert die E-Mail mit seinem privaten Schlüssel. Der Empfänger prüft die Signatur mit dem öffentlichen Schlüssel des Absenders.

Beispiele:

+ PGP (Pretty Good Privacy).
+ S/MIME (Secure/Multipurpose Internet Mail Extensions).

### Authentifizierung von SSH-Verbindungen

SSH (Secure Shell) ist ein Protokoll für den sicheren Zugriff auf entfernte Server und Systeme. Es wird häufig von Systemadministratoren und Entwicklern verwendet.

Wie funktioniert die Public-Key-Kryptographie hier?

+ Der Administrator erstellt ein **Schlüsselpaar** (privater und öffentlicher Schlüssel).
+ Der öffentliche Schlüssel wird auf dem Server gespeichert.
+ Bei der Anmeldung authentifiziert sich der Client, indem er den privaten Schlüssel verwendet, um eine Herausforderung des Servers zu lösen.
+ Dadurch wird sichergestellt, dass nur der Besitzer des privaten Schlüssels Zugriff hat.

### Blockchain-Plattformen

Eine Blockchain ist eine dezentralisierte, unveränderliche Datenbank, die Transaktionen aufzeichnet und sichert. Sie wird häufig in Kryptowährungen (z. B. Bitcoin, Ethereum) sowie in anderen Anwendungen wie Smart Contracts oder Supply-Chain-Management eingesetzt.

Wie wird Public-Key-Kryptographie in Blockchains verwendet?

+ **Wallets und Identität**: Jeder Nutzer hat ein Schlüsselpaar. Der öffentliche Schlüssel ist die Adresse der Wallet, und der private Schlüssel wird verwendet, um Transaktionen zu signieren.
+ **Digitale Signaturen**: Jede Transaktion wird mit dem privaten Schlüssel des Nutzers signiert, um ihre Authentizität sicherzustellen.
+ **Verifizierung**: Andere Knoten im Netzwerk verwenden den öffentlichen Schlüssel, um zu überprüfen, ob die Transaktion gültig ist und nicht manipuliert wurde.

Beispiele:

+ Bitcoin: Nutzer signieren Transaktionen mit ihrem privaten Schlüssel, und die Blockchain überprüft diese Signatur.
+ Ethereum: Neben der Authentifizierung von Transaktionen werden Smart Contracts ausgeführt, die ebenfalls durch Public-Key-Kryptographie gesichert sind.

## Epilog: Alice und Bob

In der Welt der Kryptographie sind **Alice** und **Bob** fiktiven Figuren, die zur Erklärung sicherer Kommunikation verwendet werden.

Hier ist die typische Vorgehensweise:

+ **Alice** ist die Absenderin **A**. Sie möchte Bob eine Nachricht senden, die privat bleiben soll.  
+ **Bob** ist der Empfänger **B**. Er soll die Nachricht erhalten, egal wer sonst noch mithört oder mitliest.  

Alice und Bob wurden erstmals in dem bahnbrechenden Papier [A Method for Obtaining Digital Signatures and Public-Key Cryptosystems](https://people.csail.mit.edu/rivest/Rsapaper.pdf) von Ronald Rivest, Adi Shamir und Leonard Adleman (den Erfindern des RSA-Algorithmus) erwähnt. Seitdem sind sie soetwas wie Kultfiguren in der Kryptographie.
	
[1]: /de/assets/img/public-key-encryption.png "Infografik Public-Key-Kryptographie"
