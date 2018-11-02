---
title: '#IF, #elif-, #else- und #endif-Direktiven (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
helpviewer_keywords:
- '#elif directive'
- conditional compilation, directives
- endif directive (#endif)
- preprocessor, directives
- '#else directive'
- '#endif directive'
- if directive (#if)
- else directive (#else)
- '#if directive'
- elif directive (#elif)
- defined directive
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
ms.openlocfilehash: 76b8be265145896105490a82946c50bc576e6f9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520421"
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if-, #elif-, #else- und #endif-Anweisungen (C/C++)

Die **#if** -Direktive, zusammen mit den **#elif**, **#else**, und **#endif** Steuerelemente-Kompilierung von Teilen einer Quelldatei-Anweisungen. Wenn der Ausdruck, die Sie schreiben (nach der **#if**) verfügt über einen Wert ungleich NULL, der Gruppe für Zeile unmittelbar nach der **#if** Richtlinie wird in der Übersetzungseinheit beibehalten.

## <a name="grammar"></a>Grammatik

*bedingte* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Elif Teile von If-Part*<sub>opt</sub> *else-Teil*<sub>opt</sub> *Endif-Zeile*

*If-Part* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*If-Line text*

*If-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if***konstanter Ausdruck*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef***Bezeichner*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef***Bezeichner*

*Elif-Teile* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Elif-Line text*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Elif-Teile Elif-Line text*

*Elif-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif***konstanter Ausdruck*

*else-Teil* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Else-Line text*

*Else-Line* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*Endif-Line-* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

Jede **#if** -Anweisung in einer Quelldatei muss eine schließende übereinstimmen **#endif** Richtlinie. Eine beliebige Anzahl von **#elif** Direktiven können angezeigt werden, zwischen den **#if** und **#endif** Direktiven, jedoch höchstens eine **#else** -Anweisung zulässig. Die **#else** Richtlinie, sofern vorhanden, muss sein die letzte Anweisung vor **#endif**.

Die **#if**, **#elif**, **#else**, und **#endif** Anweisungen können in Textteilen von anderen schachteln **#if**Anweisungen. Jede geschachtelte **#else**, **#elif**, oder **#endif** Richtlinie gehört zur nächsten vorangehenden **#if** Richtlinie.

Allen bedingten kompilierungsanweisungen, wie z. B. **#if** und **#ifdef**, müssen schließende zugeordnet werden **#endif** -Anweisungen vor dem Ende der Datei, andernfalls Fehler Nachricht wird generiert. Wenn Includedateien bedingte Kompilierungsanweisungen enthalten, müssen sie die gleichen Bedingungen erfüllen: Am Ende der Includedatei dürfen sich keine bedingten Kompilierungsanweisungen ohne Entsprechung befinden.

Makroersetzung wird ausgeführt, in dem Teil der Befehlszeile, folgt eine **#elif** Befehl, sodass ein Makroaufruf im verwendet werden kann die *Konstantenausdruck*.

Der Präprozessor wählt eines der Vorkommnisse des *Text* zur weiteren Verarbeitung. Ein im angegebenen Block *Text* kann eine beliebige Textsequenz sein. Er kann mehr als eine Zeile umfassen. In der Regel *Text* ist Programmtext, der für den Compiler oder den Präprozessor Bedeutung hat.

Der Präprozessor verarbeitet den ausgewählten *Text* und übergibt sie an den Compiler. Wenn *Text* Präprozessordirektiven, der Präprozessor enthält, werden diese Anweisungen enthält. Nur Textblöcke, die vom Präprozessor ausgewählt werden, werden kompiliert.

Der Präprozessor wählt ein einzelnes *Text* , geordnet nach der Auswertung des konstanten Ausdrucks nach jeder **#if** oder **#elif** Richtlinie bis true (ungleich null) Konstante gefunden -Ausdruck. Er wählt den gesamten Text (einschließlich anderer präprozessoranweisungen, beginnend mit **#**) bis zu der zugehörigen **#elif**, **#else**, oder **#endif** .

Wenn alle Vorkommen von *Konstantenausdruck* "false" sind oder wenn keine **#elif** -Anweisungen vorhanden sind, der Präprozessor wählt den Textblock nach der **#else** Klausel. Wenn die **#else** -Klausel weggelassen und alle Instanzen des *Konstantenausdruck* in die **#if** -Block "false", kein Textblock ausgewählt ist.

Die *Konstantenausdruck* ist ein ganzzahliger konstanter Ausdruck mit diesen zusätzlichen Einschränkungen:

- Ausdrücke müssen einen ganzzahligen Typ aufweisen und kann nur ganzzahlige Konstanten und Zeichenkonstanten enthalten und die **definiert** Operator.

- Der Ausdruck kann keinen `sizeof`-Operator oder einen Typumwandlungsoperator verwenden.

- Die Zielumgebung ist möglicherweise nicht in der Lage, alle Bereiche von ganzen Zahlen darzustellen.

- Die Übersetzung stellt Typ **Int** Typ **lange**, und **ganze Zahl ohne Vorzeichen** identisch **unsigned long**.

- Das Konvertierungsprogramm kann Zeichenkonstanten in einen Satz von Codewerten übersetzen, die sich vom Satz für die Zielumgebung unterscheiden. Um die Eigenschaften der Zielumgebung zu bestimmen, überprüfen Sie die Werte der Makros von LIMITS.H in einer für die Zielumgebung erstellten Anwendung.

- Der Ausdruck darf keine Umgebungsabfragen durchführen und muss von Implementierungsdetails auf dem Zielcomputer isoliert bleiben.

## <a name="defined"></a>Definition

Der Präprozessoroperator **definiert** kann in speziellen Konstanten Ausdrücken verwendet werden, wie in der folgenden Syntax gezeigt:

defined( `identifier` )

defined `identifier`

Dieser Konstante Ausdruck wird als "true" (ungleich null), wenn die *Bezeichner* derzeit definiert ist; andernfalls ist die Bedingung "false" (0). Ein Bezeichner, der als leerer Text definiert wird, wird als definiert betrachtet. Die **definiert** -Direktive kann verwendet werden, eine **#if** und **#elif** Richtlinie allerdings an keiner anderen Stelle.

Im folgenden Beispiel die **#if** und **#endif** Kompilierung des eine von drei Funktionsaufrufen:

```C
#if defined(CREDIT)
    credit();
#elif defined(DEBIT)
    debit();
#else
    printerror();
#endif
```

Der Funktionsaufruf an `credit` wird kompiliert, wenn der Bezeichner `CREDIT` definiert ist. Wenn der Bezeichner `DEBIT` definiert ist, wird der Funktionsaufruf an `debit` kompiliert. Wenn keiner der Bezeichner definiert ist, wird der Aufruf an `printerror` kompiliert. Beachten Sie, dass `CREDIT` und `credit` unterschiedliche Bezeichner in C und C++ sind, da ihre Groß-/Kleinschreibung unterschiedlich ist.

Die Anweisungen für die bedingte Kompilierung im folgenden Beispiel gehen von einer zuvor definierten symbolischen Konstante aus, die `DLEVEL` heißt.

```C
#if DLEVEL > 5
    #define SIGNAL  1
    #if STACKUSE == 1
        #define STACK   200
    #else
        #define STACK   100
    #endif
#else
    #define SIGNAL  0
    #if STACKUSE == 1
        #define STACK   100
    #else
        #define STACK   50
    #endif
#endif
#if DLEVEL == 0
    #define STACK 0
#elif DLEVEL == 1
    #define STACK 100
#elif DLEVEL > 5
    display( debugptr );
#else
    #define STACK 200
#endif
```

Die erste **#if** -Block zeigt zwei Sätze von verschachtelten **#if**, **#else**, und **#endif** Anweisungen. Der erste Satz von Anweisungen wird nur verarbeitet, wenn `DLEVEL > 5` "true" ist. Andernfalls die Anweisungen nach **#else** verarbeitet werden.

Die **#elif** und **#else** Anweisungen im zweiten Beispiel verwendet, um eine der vier Auswahlmöglichkeiten, basierend auf den Wert der `DLEVEL`. Die Konstante `STACK` ist auf 0, 100 oder 200 festgelegt, abhängig von der Definition von `DLEVEL`. Wenn `DLEVEL` größer als 5 ist, wird die Anweisung

```C
#elif DLEVEL > 5
display(debugptr);
```

kompiliert, und `STACK` wird nicht definiert.

Eine übliche Verwendung für die bedingte Kompilierung besteht darin, mehrere Inklusionen derselben Headerdatei zu verhindern. In C++, wo Klassen häufig in den Headerdateien definiert werden, können Konstrukte wie das folgende verwendet werden, um mehrere Definitionen zu vermeiden:

```cpp
/*  EXAMPLE.H - Example header file  */
#if !defined( EXAMPLE_H )
#define EXAMPLE_H

class Example
{
...
};

#endif // !defined( EXAMPLE_H )
```

Der vorangehende Code überprüft, ob die symbolische Konstante `EXAMPLE_H` definiert ist. In diesem Fall wurde die Datei bereits eingefügt und muss nicht erneut verarbeitet werden. Wenn dies nicht der Fall ist, wird die Konstante `EXAMPLE_H` definiert, um EXAMPLE.H als bereits verarbeitet zu markieren.

## <a name="hasinclude"></a>"__has_include"

**Visual Studio 2017 Version 15.3 und höher**: bestimmt, ob ein Header der Typbibliothek für die Aufnahme verfügbar ist:

```cpp
#ifdef __has_include
#  if __has_include(<filesystem>)
#    include <filesystem>
#    define have_filesystem 1
#  elif __has_include(<experimental/filesystem>)
#    include <experimental/filesystem>
#    define have_filesystem 1
#    define experimental_filesystem
#  else
#    define have_filesystem 0
#  endif
#endif
```

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)