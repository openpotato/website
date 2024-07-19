---
title: Einführung in Markdown
date: 2024-07-19
authors: [fstueber]
slug: was-ist-markdown
description: >
  Einführung in die grundlegenden Konzepte von Markdown.
categories:
  - Standards
---

# Einführung in Markdown

Markdown ist eine Markup-Sprache, die entwickelt wurde, um Textformatierungen einfach und lesbar zu gestalten. Es wird häufig für die Erstellung von Dokumentationen, Blogbeiträgen und anderen Texten verwendet, bei denen eine einfache Formatierung ausreicht. Dieser Blog-Artikel stellt Markdown näher vor.

<!-- more -->

## Ausgangspunkt

[Markdown](https://daringfireball.net/projects/markdown/) wurde 2004 von [John Gruber](https://github.com/gruber) in Zusammenarbeit mit [Aaron Swartz](https://en.wikipedia.org/wiki/Aaron_Swartz) entwickelt. Ziel war es, eine einfache Markup-Sprache zu schaffen, die sowohl lesbar als auch schreibbar ist, ohne den Einsatz komplizierter HTML-Tags. Der Name "Markdown" bezieht sich auf den Prozess des "vereinfachens" (englisch: "dumbing down") der Markup-Sprache, um sie benutzerfreundlicher zu gestalten. 

Markdown-Dateien sind Textdateien und haben üblicherweise die Endung `.md` oder `.markdown`.

## Grundlegende Syntax

Hier sind die grundlegenden Elemente von Markdown.

### Überschriften

Überschriften werden mit dem Zeichen `#` markiert. Die Anzahl der `#` bestimmt die Ebene der Überschrift.

Beispiele:

```
# H1 Überschrift
## H2 Überschrift
### H3 Überschrift
#### H4 Überschrift
##### H5 Überschrift
###### H6 Überschrift
```

### Fett und Kursiv

Text kann **fett** oder *kursiv* formatiert werden.

Beispiele:

```
*kursiv* oder _kursiv_
**fett** oder __fett__
***fett und kursiv*** oder ___fett und kursiv___
```

### Listen

Es gibt ungeordnete und geordnete Listen.

Beispiele:

```
Das ist eine ungeordnete Liste:
- Ein Punkt
- Noch ein Punkt
    - Unterpunkt

Das ist eine geordnete Liste:
1. Erster Punkt
2. Zweiter Punkt
    1. Unterpunkt
```

### Verweise

Verweise werden in eckigen Klammern `[Text]` und runden Klammern `(URL)` geschrieben.

Beispiel:

```
[OpenPotato](https://www.openpotato.org)
```

### Bilder

Bilder werden ähnlich wie Verweise eingefügt, aber mit einem vorangestellten `!`.

Beispiel:

```
![OpenPotato-Logo](https://www.openpotato.org/de/assets/logos/logo.svg)
```

### Zitate

Zitate werden mit `>` markiert.

Beispiel:

```
> Dies ist ein Zitat.
```

### Code

Für Inline-Code verwendet man Backticks `` ` ``.

Beispiel:

```
Dies ist ein `Inline-Code`.
```

Codeblöcke können mit drei Backticks oder durch Einrücken des Textes mit vier Leerzeichen erstellt werden.

Beispiel:

````
``` 
def hallo_welt():
    print("Hallo Welt")
```
````

### Tabellen

Tabellen können mit `|` und `-` erstellt werden.

Beispiel:

```
| Überschrift 1 | Überschrift 2 |
| ------------- | ------------- |
| Zelle 1       | Zelle 2       |
| Zelle 3       | Zelle 4       |
```

### Absätze

Absätze in Markdown werden durch eine oder mehrere Leerzeilen getrennt. Eine leere Zeile zwischen zwei Textblöcken erzeugt zwei separate Absätze.

Beispiel:

```
Dies ist der erste Absatz.

Dies ist der zweite Absatz.
```

### Zeilenumbrüche

In Markdown wird ein einzelner Zeilenumbruch (Eingabetaste) innerhalb eines Absatzes in der Regel ignoriert. Um tatsächlich einen Zeilenumbruch zu erzeugen, muss man zwei Leerzeichen am Ende der Zeile einfügen und dann die Eingabetaste drücken.

Beispiel (beachte die zwei Leerzeichen am Ende der ersten Zeile):

```
Dies ist die erste Zeile.  
Dies ist die zweite Zeile.
```

Ein anderer Weg, um einen Zeilenumbruch zu erzwingen, ist die Verwendung des HTML-`<br>`-Tags (siehe auch Abschnitt *Inline-HTML*). Dies ist besonders nützlich, wenn man komplexere Dokumente schreibt oder sicherstellen möchte, dass der Zeilenumbruch unabhängig vom verwendeten Markdown-Parser korrekt dargestellt wird.

Beispiel:

```
Dies ist die erste Zeile.<br>Dies ist die zweite Zeile.
```

### Escape-Syntax

In Markdown gibt es bestimmte Zeichen und Zeichenfolgen, die eine spezielle Bedeutung haben und zur Formatierung von Text verwendet werden, wie z.B. `*` für kursiven Text oder `#` für Überschriften. Manchmal möchte man jedoch diese Zeichen als normale Textzeichen darstellen. Hier kommt der Escape-Syntax ins Spiel, der es ermöglicht, die spezielle Bedeutung dieser Zeichen aufzuheben.

Um ein spezielles Zeichen in Markdown als normales Zeichen darzustellen, verwendet man den Backslash (`\`). Der Backslash signalisiert Markdown, dass das darauf folgende Zeichen als normales Zeichen behandelt werden soll.

Beispiele:

- **Asterisk (\*)**:
  ```
  \*Dieser Text ist nicht kursiv\*
  ```
  Wird dargestellt als: \*Dieser Text ist nicht kursiv\*

- **Unterstrich (\_)**:
  ```
  \_Dieser Text ist nicht kursiv\_
  ```
  Wird dargestellt als: \_Dieser Text ist nicht kursiv\_

- **Hash (\#)**:
  ```
  \# Dies ist keine Überschrift
  ```
  Wird dargestellt als: \# Dies ist keine Überschrift

- **Backtick (\`)**:
  ```
  \`Dies ist kein Inline-Code\`
  ```
  Wird dargestellt als: \`Dies ist kein Inline-Code\`

- **Backslash (\\)**:
  ```
  Dies ist ein Backslash: \\
  ```
  Wird dargestellt als: Dies ist ein Backslash: \\

### Trennlinien

Mit Trennlinien oder horizontalen Linien können Inhalte visuell getrennt werden. 

Es gibt mehrere Möglichkeiten, eine horizontale Linie in Markdown zu erstellen. Diese Methoden umfassen die Verwendung von drei oder mehr Bindestrichen (`-`), Unterstrichen (`_`) oder Sternchen (`*`). Zwischen diesen Zeichen können optional Leerzeichen eingefügt werden.

Beispiel mit Bindestrichen:

```
Dies ist Text oberhalb der Trennlinie.
---
Dies ist Text unterhalb der Trennlinie.
```

Beispiel mit Sternchen und Leerzeichen:

```
Dies ist Text oberhalb der Trennlinie.

* * *

Dies ist Text unterhalb der Trennlinie.
```

### Inline-HTML

Markdown-Dateien werden üblicherweise als HTML gerendert, und jedes gültige HTML-Tag kann innerhalb eines Markdown-Dokuments verwendet werden. Dies ermöglicht erweiterte Formatierungen, die mit der nativen Markdown-Syntax nicht möglich sind.

Beispiel:

```
Dies ist ein normaler Absatz in Markdown.

<div style="color: red;">Dieser Text ist rot und in einem div-Tag.</div>

<p>Dies ist ein Absatz im HTML-Format.</p>
```

## Erweiterungen und Dialekte

Markdown hat mehrere Dialekte und Erweiterungen, die zusätzliche Funktionalitäten bieten. Hier sind zwei Beispiele:

### GitHub Flavored Markdown (GFM)

[GitHub](https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) hat Markdown um einige nützliche Features erweitert.

#### Task Lists

Aufgabenlisten können mit `[ ]` und `[x]` erstellt werden.

Beispiel:

```
- [x] Aufgabe 1
- [ ] Aufgabe 2
```

#### Syntax-Highlighting

GitHub unterstützt Syntax-Highlighting für verschiedene Programmiersprachen in Codeblöcken.

Hier ein Beispiel für Python-Code:

````
```python
def hallo_welt():
    print("Hallo Welt")
```
````

#### Strikethrough

Durchgestrichener Text kann mit `~~` erstellt werden.

Beispiel:

```
~~Dieser Text ist durchgestrichen~~
```

### Pandoc Markdown

[Pandoc](https://pandoc.org/MANUAL.html#pandocs-markdown) ist ein Werkzeug zur Konvertierung von Markdown in viele verschiedene Formate. Es erweitert Markdown um zusätzliche Features, wie z.B. Fußnoten und mathematische Formeln.

#### Fußnoten

Eine Fußnote ist eine Quellenangabe oder Anmerkung, die unter dem Fließtext einer Seite steht.

Beispiel:

```
Dies ist ein Beispieltext mit einer Fußnote[^1].

[^1]: Das ist die Fußnote.
```

#### Mathematische Formeln

Mathematische Formeln können in Pandoc mit LaTeX-Syntax eingefügt werden.

Beispiele:

```	
Ein Inline-Mathematikbeispiel: \(E = mc^2\)

Ein Block-Mathematikbeispiel:
$$
E = mc^2
$$
```

### Cheatsheet

Zum Thema *Markdown* gibt es einen nützlichen [Spickzettel (cheatsheet)](https://github.com/lifeparticle/Markdown-Cheatsheet/blob/main/README.md) mit vielen zusätzlichen Nuancen. 
