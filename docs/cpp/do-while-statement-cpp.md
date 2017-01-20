---
title: "do-while-Anweisung (C++)"
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
  - "do-while_cpp"
  - "do-while"
  - "do"
  - "while_cpp"
  - "do_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "do-Schlüsselwort [C++]"
  - "do-Schlüsselwort [C++], do-while"
  - "do-while-Schlüsselwort [C++]"
  - "while-Schlüsselwort [C++], do-while"
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# do-while-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt eine *Anweisung* wiederholt aus, bis die angegebene Beendigungsbedingung \(der *Ausdruck*\) als 0 \(null\) ausgewertet wird.  
  
## Syntax  
  
```  
  
      do  
   statement  
   while ( expression ) ;  
```  
  
## Hinweise  
 Der Test der Beendigungsbedingung wird nach jeder Ausführung der Schleife durchgeführt. Daher wird eine `do-while`\-Schleife einmal oder mehrmals ausgeführt, abhängig vom Wert des Beendigungsausdrucks.  Die `do-while`\-Anweisung kann auch beendet werden, wenn eine [break](../cpp/break-statement-cpp.md)\-, eine [goto](../cpp/goto-statement-cpp.md)\- oder eine [return](../cpp/return-statement-cpp.md)\-Anweisung innerhalb des Anweisungstexts ausgeführt wird.  
  
 Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen.  Die Ausführung erfolgt folgendermaßen:  
  
1.  Der Anweisungstext wird ausgeführt.  
  
2.  Danach wird *expression*, der Ausdruck, ausgewertet.  Wenn *expression* "false" ist, wird die `do-while`\-Anweisung beendet und das Steuerelement an die nächste Anweisung im Programm weitergegeben.  Wenn *expression* "true" \(ungleich 0 \(null\)\) ist, wird der Prozess wiederholt, beginnend mit Schritt 1.  
  
## Beispiel  
 Die `do-while`\-Anweisung wird im folgenden Beispiel veranschaulicht:  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## Siehe auch  
 [Iterationsanweisungen](../cpp/iteration-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [while\-Anweisung \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [for\-Anweisung \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [Bereichsbasiert für Anweisung \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)