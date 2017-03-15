---
title: "#if-, #elif-, #else- und #endif-Direktiven (C/C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "#else"
  - "#endif"
  - "#if"
  - "#elif"
  - "Defined"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#elif-Direktive"
  - "#else-Direktive"
  - "#endif-Direktive"
  - "#if-Direktive"
  - "Bedingte Kompilierung, Direktiven"
  - "defined-Direktive"
  - "elif-Direktive (#elif)"
  - "else-Direktive (#else)"
  - "endif-Direktive (#endif)"
  - "if-Direktive (#if)"
  - "Präprozessor, Direktiven"
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# #if-, #elif-, #else- und #endif-Direktiven (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `#if`\-Direktive steuert mit den Direktiven `#elif`, `#else` und `#endif` die Kompilierung von Teilen einer Quelldatei.  Wenn der Ausdruck, den Sie schreiben \(nach `#if`\), einen Wert ungleich 0 \(null\) aufweist, wird die Zeilengruppe, die unmittelbar auf die `#if`\-Direktive folgt, in der Übersetzungseinheit beibehalten.  
  
## Grammatik  
 *conditional* :  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part* :  
 *if\-line text*  
  
 *if\-line* :  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts* :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line* :  
 **\#elif**  *constant\-expression*  
  
 *else\-part* :  
 *else\-line text*  
  
 *else\-line* :  
 `#else`  
  
 *endif\-line* :  
 `#endif`  
  
 Jeder `#if`\-Direktive in einer Quelldatei muss eine schließende `#endif`\-Direktive zugeordnet sein.  Eine beliebige Anzahl von `#elif`\-Direktiven kann zwischen der `#if`\- und der `#endif`\-Direktive auftreten, es ist jedoch höchstens eine `#else`\-Direktive zulässig.  Die `#else`\-Direktive muss, falls vorhanden, die letzte Direktive vor `#endif` sein.  
  
 Die Direktiven `#if`, `#elif`, `#else` und `#endif` können in Textteilen von anderen `#if`\-Direktiven geschachtelt sein.  Jede geschachtelte Direktive `#else`, `#elif` oder `#endif` gehört zur nächsten vorangehenden `#if`\-Direktive.  
  
 Allen bedingten Kompilierungsdirektiven, wie `#if` und **\#ifdef**, müssen schließende `#endif`\-Direktiven vor dem Dateiende zugeordnet sein; andernfalls wird eine Fehlermeldung generiert.  Wenn Includedateien bedingte Kompilierungsdirektiven enthalten, müssen sie die gleichen Bedingungen erfüllen: Am Ende der Includedatei dürfen sich keine bedingten Kompilierungsdirektiven ohne Entsprechung befinden.  
  
 Makroersetzung wird innerhalb des Teils der Befehlszeile ausgeführt, die einem `#elif`\-Befehl folgt, sodass ein Makroaufruf im *constant\-expression*, im konstanten Ausdruck, verwendet werden kann.  
  
 Der Präprozessor wählt eines der Vorkommnisse von *text* für die weitere Verarbeitung aus.  Ein Block, der in *text* angegeben ist, kann eine beliebige Textsequenz sein.  Er kann mehr als eine Zeile umfassen.  Normalerweise handelt es sich bei *text* um Programmtext, der für den Compiler oder den Präprozessor von Bedeutung ist.  
  
 Der Präprozessor verarbeitet den ausgewählten *text* und übergibt ihn an den Compiler.  Wenn der *text* Präprozessordirektiven enthält, werden diese Direktiven vom Präprozessor ausgeführt.  Nur Textblöcke, die vom Präprozessor ausgewählt werden, werden kompiliert.  
  
 Der Präprozessor wählt ein einzelnes *text*\-Element aus, indem er den konstanten Ausdruck nach jeder `#if`\- oder `#elif`\-Direktive auswertet, bis er einen konstanten Ausdruck mit dem Wert "true" \(ungleich 0 \(null\)\) findet.  Er wählt den gesamten Text \(einschließlich anderer Präprozessordirektiven, die mit **\#** beginnen\) bis zu der ihm zugeordneten `#elif`, `#else` oder `#endif` aus.  
  
 Wenn alle Vorkommnisse von *constant\-expression* "false" sind oder wenn keine `#elif`\-Direktiven vorhanden sind, wählt der Präprozessor den Textblock nach der `#else`\-Klausel aus.  Wenn die `#else`\-Klausel ausgelassen wird und alle Instanzen von *constant\-expression* im `#if`\-Block "false" sind, wird kein Textblock ausgewählt.  
  
 *constant\-expression* ist ein ganzzahliger konstanter Ausdruck mit diesen zusätzlichen Einschränkungen:  
  
-   Ausdrücke müssen einen ganzzahligen Typ aufweisen und können nur ganzzahlige Konstanten und Zeichenkonstanten und den **defined** \-Operator umfassen.  
  
-   Der Ausdruck kann keinen `sizeof`\-Operator oder einen Typumwandlungsoperator verwenden.  
  
-   Die Zielumgebung ist möglicherweise nicht in der Lage, alle Bereiche von ganzen Zahlen darzustellen.  
  
-   Die Übersetzung stellt Typ `int` wie Typ **long** und Typ `unsigned int` wie Typ `unsigned long` dar.  
  
-   Das Konvertierungsprogramm kann Zeichenkonstanten in einen Satz von Codewerten übersetzen, die sich vom Satz für die Zielumgebung unterscheiden.  Um die Eigenschaften der Zielumgebung zu bestimmen, überprüfen Sie die Werte der Makros von LIMITS.H in einer für die Zielumgebung erstellten Anwendung.  
  
-   Der Ausdruck darf keine Umgebungsabfragen durchführen und muss von Implementierungsdetails auf dem Zielcomputer isoliert bleiben.  
  
 Der Präprozessoroperator **defined** kann in speziellen konstanten Ausdrücken verwendet werden, wie in der folgenden Syntax gezeigt:  
  
 defined\( `identifier` \)  
  
 defined `identifier`  
  
 Dieser konstante Ausdruck wird als "true" \(ungleich 0 \(null\)\) ausgewertet, wenn *identifier*, der Bezeichner, derzeit definiert ist; andernfalls ist die Bedingung "false" \(0\).  Ein Bezeichner, der als leerer Text definiert wird, wird als definiert betrachtet.  Die **defined**\-Direktive kann in einer `#if`\- und einer `#elif`\-Direktive verwendet werden, jedoch an keiner anderen Stelle.  
  
 Im folgenden Beispiel steuern die `#endif`\-Direktive und die `#if`\-Direktive die Kompilierung von einem von drei Funktionsaufrufen:  
  
```  
#if defined(CREDIT)  
    credit();  
#elif defined(DEBIT)  
    debit();  
#else  
    printerror();  
#endif  
```  
  
 Der Funktionsaufruf an `credit` wird kompiliert, wenn der Bezeichner `CREDIT` definiert ist.  Wenn der Bezeichner `DEBIT` definiert ist, wird der Funktionsaufruf an `debit` kompiliert.  Wenn keiner der Bezeichner definiert ist, wird der Aufruf an `printerror` kompiliert.  Beachten Sie, dass `CREDIT` und `credit` unterschiedliche Bezeichner in C und C\+\+ sind, da ihre Groß\-\/Kleinschreibung unterschiedlich ist.  
  
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
  
 Der erste `#if`\-Block zeigt zwei Sätze von verschachtelten `#if`\-, `#else`\- und `#endif`\-Direktiven.  Der erste Satz von Direktiven wird nur verarbeitet, wenn `DLEVEL > 5` "true" ist.  Andernfalls werden die Anweisungen nach \#**else** verarbeitet.  
  
 Die Direktiven `#elif` und `#else` im zweiten Beispiel werden verwendet, um eine von vier Auswahlmöglichkeiten zu treffen, abhängig vom Wert von `DLEVEL`.  Die Konstante `STACK` ist auf 0, 100 oder 200 festgelegt, abhängig von der Definition von `DLEVEL`.  Wenn `DLEVEL` größer als 5 ist, wird die Anweisung  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 kompiliert, und `STACK` wird nicht definiert.  
  
 Eine übliche Verwendung für die bedingte Kompilierung besteht darin, mehrere Inklusionen derselben Headerdatei zu verhindern.  In C\+\+, wo Klassen häufig in den Headerdateien definiert werden, können Konstrukte wie das folgende verwendet werden, um mehrere Definitionen zu vermeiden:  
  
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
  
 Der vorangehende Code überprüft, ob die symbolische Konstante `EXAMPLE_H` definiert ist.  In diesem Fall wurde die Datei bereits eingefügt und muss nicht erneut verarbeitet werden.  Wenn dies nicht der Fall ist, wird die Konstante `EXAMPLE_H` definiert, um EXAMPLE.H als bereits verarbeitet zu markieren.  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)