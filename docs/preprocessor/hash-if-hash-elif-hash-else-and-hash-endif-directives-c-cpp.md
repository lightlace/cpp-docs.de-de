---
title: '#<a name="if-elif-else-and-endif-directives-cc--microsoft-docs"></a>IF, #elif-, #else- und #endif-Direktiven (C/C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
dev_langs: C++
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
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 01dc273b4c878db4ba48ce38bf69919eb2bfae3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if-, #elif-, #else- und #endif-Anweisungen (C/C++)
Die `#if`-Direktive steuert mit den Direktiven `#elif`, `#else` und `#endif` die Kompilierung von Teilen einer Quelldatei. Wenn der Ausdruck, den Sie schreiben (nach `#if`), einen Wert ungleich 0 (null) aufweist, wird die Zeilengruppe, die unmittelbar auf die `#if`-Direktive folgt, in der Übersetzungseinheit beibehalten.  
  
## <a name="grammar"></a>Grammatik  
 *bedingte* :  
 *If-Teil Elif-Teile*opt*else-Teil*opt*Endif-Zeile*  
  
 *If-Teil* :  
 *If-Line-text*  
  
 *If-Line-* :  
 **#if***Konstantenausdruck*   
  
 **#ifdef***Bezeichner*   
  
 **#ifndef***Bezeichner*   
  
 *Elif-Teile* :  
 *Elif-Line-text*  
  
 *Elif-Teile Elif-Line-text*  
  
 *Elif-Line-* :  
 **#elif***Konstantenausdruck*   
  
 *else-Teil* :  
 *Else-Line-text*  
  
 *Else-Line* :  
 `#else`  
  
 *Endif-Line-* :  
 `#endif`  
  
 Jeder `#if`-Direktive in einer Quelldatei muss eine schließende `#endif`-Direktive zugeordnet sein. Eine beliebige Anzahl von `#elif`-Direktiven kann zwischen der `#if`- und der `#endif`-Direktive auftreten, es ist jedoch höchstens eine `#else`-Direktive zulässig. Die `#else`-Direktive muss, falls vorhanden, die letzte Direktive vor `#endif` sein.  
  
 Die Direktiven `#if`, `#elif`, `#else` und `#endif` können in Textteilen von anderen `#if`-Direktiven geschachtelt sein. Jede geschachtelte Direktive `#else`, `#elif` oder `#endif` gehört zur nächsten vorangehenden `#if`-Direktive.  
  
 Allen bedingten Kompilierungsdirektiven, wie z. B. `#if` und **#ifdef**, müssen schließende zugeordnet werden `#endif` -Direktiven vor dem Dateiende; andernfalls wird eine Fehlermeldung generiert. Wenn Includedateien bedingte Kompilierungsanweisungen enthalten, müssen sie die gleichen Bedingungen erfüllen: Am Ende der Includedatei dürfen sich keine bedingten Kompilierungsanweisungen ohne Entsprechung befinden.  
  
 Makroersetzung wird ausgeführt, in dem Teil der Befehlszeile, folgt eine `#elif` Befehls, sodass ein Makroaufruf im verwendet werden kann die *Konstantenausdruck*.  
  
 Der Präprozessor wählt eines der Vorkommnisse von *Text* zur weiteren Verarbeitung. Ein im angegebenen Block *Text* kann eine beliebige Textsequenz sein. Er kann mehr als eine Zeile umfassen. In der Regel *Text* ist Programmtext, der für den Compiler oder den Präprozessor Bedeutung hat.  
  
 Der Präprozessor verarbeitet den ausgewählten *Text* und übergibt sie an den Compiler. Wenn *Text* enthält, werden diese Direktiven vom Präprozessor ausgeführt. Nur Textblöcke, die vom Präprozessor ausgewählt werden, werden kompiliert.  
  
 Der Präprozessor wählt ein einzelnes *Text* Element durch das Auswerten der Konstanten Ausdrucks nach jeder `#if` oder `#elif` Richtlinie, bis einen "true" (ungleich null) Konstanten Ausdruck gefunden wird. Er wählt den gesamten Text (einschließlich anderer Präprozessordirektiven, beginnend mit  **#** ) bis zu seiner zugeordneten `#elif`, `#else`, oder `#endif`.  
  
 Wenn alle Vorkommen von *Konstantenausdruck* "false" sind oder wenn keine `#elif` -Direktiven vorhanden sind, wählt der Präprozessor den Textblock nach der `#else` Klausel. Wenn die `#else` -Klausel weggelassen, und alle Instanzen des *Konstantenausdruck* in die `#if` -Block "false" sind, kein Textblock ausgewählt ist.  
  
 Die *Konstantenausdruck* ist ein ganzzahliger konstanter Ausdruck mit diesen zusätzlichen Einschränkungen:  
  
-   Ausdrücke müssen einen ganzzahligen Typ aufweisen und können nur ganzzahlige Konstanten, Zeichenkonstanten, einschließen und die **definiert** Operator.  
  
-   Der Ausdruck kann keinen `sizeof`-Operator oder einen Typumwandlungsoperator verwenden.  
  
-   Die Zielumgebung ist möglicherweise nicht in der Lage, alle Bereiche von ganzen Zahlen darzustellen.  
  
-   Die Übersetzung stellt Typ `int` Typ **lange**, und `unsigned int` identisch `unsigned long`.  
  
-   Das Konvertierungsprogramm kann Zeichenkonstanten in einen Satz von Codewerten übersetzen, die sich vom Satz für die Zielumgebung unterscheiden. Um die Eigenschaften der Zielumgebung zu bestimmen, überprüfen Sie die Werte der Makros von LIMITS.H in einer für die Zielumgebung erstellten Anwendung.  
  
-   Der Ausdruck darf keine Umgebungsabfragen durchführen und muss von Implementierungsdetails auf dem Zielcomputer isoliert bleiben.  

## <a name="defined"></a>Definition  
 Der Präprozessoroperator **definiert** in speziellen Konstanten Ausdrücken verwendet werden können, wie in der folgenden Syntax gezeigt:  
  
 defined( `identifier` )  
  
 defined `identifier`  
  
 Dieser Konstante Ausdruck wird als "true" (ungleich null), wenn die *Bezeichner* derzeit definiert ist; andernfalls ist die Bedingung "false" (0). Ein Bezeichner, der als leerer Text definiert wird, wird als definiert betrachtet. Die **definiert** -Direktive kann verwendet werden, eine `#if` und ein `#elif` Richtlinie jedoch an keiner anderen Stelle.  
  
 Im folgenden Beispiel steuern die `#if`-Direktive und die `#endif`-Direktive die Kompilierung von einem von drei Funktionsaufrufen:  
  
```  
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
  
```  
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
  
 Der erste `#if`-Block zeigt zwei Sätze von verschachtelten `#if`-, `#else`- und `#endif`-Direktiven. Der erste Satz von Direktiven wird nur verarbeitet, wenn `DLEVEL > 5` "true" ist. Andernfalls, die Anweisungen nach #**else** verarbeitet werden.  
  
 Die Direktiven `#elif` und `#else` im zweiten Beispiel werden verwendet, um eine von vier Auswahlmöglichkeiten zu treffen, abhängig vom Wert von `DLEVEL`. Die Konstante `STACK` ist auf 0, 100 oder 200 festgelegt, abhängig von der Definition von `DLEVEL`. Wenn `DLEVEL` größer als 5 ist, wird die Anweisung  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 kompiliert, und `STACK` wird nicht definiert.  
  
 Eine übliche Verwendung für die bedingte Kompilierung besteht darin, mehrere Inklusionen derselben Headerdatei zu verhindern. In C++, wo Klassen häufig in den Headerdateien definiert werden, können Konstrukte wie das folgende verwendet werden, um mehrere Definitionen zu vermeiden:  
  
```  
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

## <a name="hasinclude"></a>__has_include
**Visual Studio 2017 15,3 und höher**: bestimmt, ob ein Header der Typbibliothek für die Aufnahme verfügbar ist:  

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