---
title: "continue-Anweisung (C)"
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
  - "continue"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "continue-Schlüsselwort [C]"
  - "Schleifenstruktur, continue-Schlüsselwort"
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# continue-Anweisung (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `continue`\-Anweisung übergibt die Steuerung an die nächste Iteration der nächsten einschließenden `do`\-, `for`\- oder `while`\-Anweisung, in der sie angezeigt wird, und umgeht alle verbleibenden Anweisungen im `do`\-, `for`\- oder `while`\-Anweisungstext.  
  
## Syntax  
 `jump-statement`:  
 `continue;`  
  
 Die nächste Iteration einer `do`\-, `for`\- oder `while`\-Anweisungen wird wie folgt bestimmt:  
  
-   Innerhalb einer `do`\-Anweisung oder einer `while`\-Anweisung wird die nächste Iteration mit einer erneuten Auswertung des Ausdrucks der `do`\-Anweisung oder der `while`\-Anweisung begonnen.  
  
-   Eine `continue`\-Anweisung in einer `for`\-Anweisung führt dazu, dass der Schleifenausdruck der `for`\-Anweisung ausgewertet wird.  Anschließend wertet der Compiler den bedingten Ausdruck neu aus und beendet oder durchläuft den Anweisungstext je nach Ergebnis.  Weitere Informationen zur `for`\-Anweisung und den Nichtterminalen finden Sie in der [for\-Anweisung](../c-language/for-statement-c.md).  
  
 In diesem Beispiel wird die `continue`\-Anweisung veranschaulicht:  
  
```  
while ( i-- > 0 )   
{  
    x = f( i );  
    if ( x == 1 )  
        continue;  
    y += x * x;  
}  
```  
  
 In diesem Beispiel wird der Anweisungstext ausgeführt, während `i` größer als 0 ist.  Zunächst wird `f(i)` `x` zugewiesen. Wenn `x` gleich 1 ist, wird dann die `continue`\-Anweisung ausgeführt.  Die übrigen Anweisungen im Text werden ignoriert, und die Ausführung wird am Anfang der Schleife mit der Auswertung des Schleifentests fortgesetzt.  
  
## Siehe auch  
 [continue\-Anweisung](../cpp/continue-statement-cpp.md)