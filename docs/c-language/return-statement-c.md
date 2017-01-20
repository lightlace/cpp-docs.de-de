---
title: "return-Anweisung (C)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "( )-Klammern in return-Anweisungen"
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# return-Anweisung (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mithilfe der `return`\-Anweisung wird die Ausführung einer Funktion beendet, und die Steuerung wird an die aufrufende Funktion zurückgegeben.  Die Ausführung wird in der aufrufenden Funktion an dem Punkt fortgesetzt, der dem Aufruf unmittelbar folgt.  Eine `return`\-Anweisung kann den Wert auch an die aufrufende Funktion zurückgeben.  Weitere Informationen finden Sie unter [Rückgabetyp](../c-language/return-type.md).  
  
## Syntax  
 *Sprunganweisung*:  
 **return**  *expression*  opt **;**  
  
 Der Wert von *expression* wird, sofern er vorhanden ist, an die aufrufende Funktion zurückgegeben.  Wenn *expression* ausgelassen wird, wird der Rückgabewert der Funktion nicht definiert.  Der Ausdruck wird, sofern er vorhanden ist, ausgewertet und dann in den von der Funktion zurückgegebenen Typ konvertiert.  Wenn die Funktion mit Rückgabetyp `void` deklariert wurde, generiert eine `return`\-Anweisung, die einen Ausdruck enthält, eine Warnung, und der Ausdruck wird nicht ausgewertet.  
  
 Wenn keine `return`\-Anweisung in einer Funktionsdefinition steht, kehrt die Steuerung nach Ausführen der letzten Anweisung der aufgerufenen Funktion automatisch zur aufrufenden Funktion zurück.  In diesem Fall ist der Rückgabewert der aufgerufenen Funktion nicht definiert.  Ist der Rückgabewert nicht erforderlich, deklarieren Sie die Funktion mit dem Rückgabetyp `void`. Andernfalls ist der Rückgabetyp `int`.  
  
 Viele Programmierer schließen das *expression*\-Argument der `return`\-Anweisung in Klammern ein.  Allerdings erfordert C die Klammern nicht.  
  
 In diesem Beispiel wird die `return`\-Anweisung veranschaulicht.  
  
```  
#include <limits.h>  
#include <stdio.h>  
  
void draw( int i, long long ll );  
long long sq( int s );  
  
int main()  
{  
    long long y;  
    int x = INT_MAX;  
  
    y = sq( x );  
    draw( x, y );  
    return x;  
}  
  
long long sq( int s )  
{  
    // Note that parentheses around the return expression   
    // are allowed but not required here.  
    return( s * (long long)s );  
}  
  
void draw( int i, long long ll )  
{  
    printf( "i = %d, ll = %lld\n", i, ll );  
    return;  
}  
  
```  
  
 In diesem Beispiel werden von der `main`\-Funktion zwei Funktionen aufgerufen: `sq` und `draw`.  Die `sq`\-Funktion gibt den Wert von `x * x` an `main` zurück. Dort wird der Rückgabewert `y` zugewiesen.  Die Klammern um den Rückgabeausdruck in `sq` werden als Teil des Ausdrucks ausgewertet und sind für die return\-Anweisung nicht erforderlich.  Da der Rückgabeausdruck vor der Konvertierung in den Rückgabetyp ausgewertet wird, erzwingt `sq` zur Vermeidung eines möglichen Ganzzahlüberlaufs, der zu unerwarteten Ergebnissen führen könnte, den Ausdruckstyp mit einer Umwandlung der Rückgabetyp zu sein.  Die Funktion `draw` wird als `void`\-Funktion deklariert.  Sie gibt die Werte der Parameter aus, und die Funktion wird dann von der leeren return\-Anweisung beendet, und es wird kein Wert zurückgegeben.  Ein Versuch, den Rückgabewert von `draw` zuzuweisen, würde die Ausgabe einer Diagnosemeldung bewirken.  Die `main`\-Funktion gibt dann den Wert `x` an das Betriebssystem zurück.  
  
 Die Ausgabe der Beispiele sieht wie folgt aus:  
  
  **i \= 2147483647, ll \= 4611686014132420609**   
## Siehe auch  
 [Anweisungen](../c-language/statements-c.md)