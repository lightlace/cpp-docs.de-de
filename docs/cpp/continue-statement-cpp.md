---
title: "continue-Anweisung (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "continue"
  - "continue_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "continue-Schlüsselwort [C++]"
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# continue-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erzwingt die Übertragung der Steuerung an den steuernden Ausdruck der kleinsten einschließenden [Do](../cpp/do-while-statement-cpp.md)\-, [For](../cpp/for-statement-cpp.md)\- oder [While](../cpp/while-statement-cpp.md)\-Schleife.  
  
## Syntax  
  
```  
continue;  
```  
  
## Hinweise  
 Alle verbleibenden Anweisungen in der aktuellen Iteration werden nicht ausgeführt.  Die nächste Iteration der Schleife wird wie folgt bestimmt:  
  
-   In einer `do`\- oder `while`\-Schleife wird die nächste Iteration mit einer erneuten Auswertung des steuernden Ausdrucks der `do`\- oder der `while`\-Anweisung begonnen.  
  
-   In einer `for`\-Schleife \(mit der Syntax `for`\(`init-expr`; `cond-expr`; `loop-expr`\)\), wird die `loop-expr`\-Klausel ausgeführt.  Anschließend wird die `cond-expr`\-Klausel neu ausgewertet und, je nach Ergebnis, wird die Schleife entweder beendet oder es tritt eine andere Iteration auf.  
  
 Das folgende Beispiel zeigt, wie die `continue`\-Anweisung verwendet werden kann, um Abschnitte des Codes zu umgehen und die Iteration der nächsten Schleife zu starten.  
  
## Beispiel  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
  **vor dem Fortsetzen**  
**vor dem Fortsetzen**  
**vor dem Fortsetzen**  
**nach der Do\-Schleife**   
## Siehe auch  
 [Sprunganweisungen](../cpp/jump-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)