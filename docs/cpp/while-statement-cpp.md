---
title: "while-Anweisung (C++)"
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
  - "while_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "while-Schlüsselwort [C++]"
  - "while-Schlüsselwort [C++], Syntax"
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# while-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt *Anweisung* so lange aus, bis *Ausdruck* mit Null ausgewertet wird.  
  
## Syntax  
  
```  
  
      while ( expression )  
   statement  
```  
  
## Hinweise  
 Der *Ausdruck* wird vor jeder Ausführung der Schleife getestet. Deshalb wird eine `while`\-Schleife nie oder mehrmals ausgeführt.  *Ausdruck* muss ein Ganzzahltyp, ein Zeigertyp oder ein Klassentyp mit einer eindeutigen Konvertierung in einen Ganzzahl\- oder Zeigertyp sein.  
  
 Eine `while`\-Schleife kann auch beendet werden, wenn innerhalb des Anweisungstexts [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) oder [return](../cpp/return-statement-cpp.md) ausgeführt wird.  Verwenden Sie [continue](../cpp/continue-statement-cpp.md) zum Beenden der aktuelle Iteration, ohne auch die `while`\-Schleife zu beenden.  Mit **continue** wird die Steuerung an die nächste Iteration der `while`\-Schleife übergeben.  
  
 Im folgenden Code wird eine `while`\-Schleife verwendet, um nachstehende Unterstriche von einer Zeichenfolge abzuschneiden:  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 Die Beendigungsbedingung wird am Anfang der Schleife ausgewertet.  Solange keine nachgestellten Unterstriche vorhanden sind, wird die Schleife nicht ausgeführt.  
  
## Siehe auch  
 [Iterationsanweisungen](../cpp/iteration-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [do\-while\-Anweisung \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [for\-Anweisung \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [Bereichsbasiert für Anweisung \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)