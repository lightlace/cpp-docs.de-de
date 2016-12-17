---
title: "goto-Anweisung (C++)"
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
  - "goto_cpp"
  - "goto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "goto-Schlüsselwort [C++]"
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# goto-Anweisung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `goto`\-Anweisung überträgt ohne Bedingungen das Steuerelement an die Anweisung, die vom festgelegten Bezeichner angegeben wurde.  
  
## Syntax  
  
```  
goto identifier;  
```  
  
## Hinweise  
 Die bezeichnete Anweisung, die durch `identifier` angegeben wird, muss sich in der aktuellen Funktion befinden.  Alle `identifier`\-Namen sind Member eines internen Namespace und beeinträchtigen daher andere Bezeichner nicht.  
  
 Eine Anweisungsbezeichnung ist nur im Fall einer `goto`\-Anweisung sinnvoll; andernfalls werden Anweisungsbezeichnungen ignoriert.  Bezeichnungen können nicht erneut deklariert werden.  
  
 Zu Programmierzwecken wird empfohlen, wann immer möglich die Anweisungen `break`, `continue` und `return` anstelle der `goto`\-Anweisung zu verwenden.  Da die `break`\-Anweisung nur eine Ebene einer Schleife beendet, müssen Sie möglicherweise eine `goto`\-Anweisung verwenden, um eine tief geschachtelte Schleife zu beenden.  
  
 Weitere Informationen über Bezeichnungen und die `goto`\-Anweisung finden Sie unter [Anweisungen mit Bezeichnung](../cpp/labeled-statements.md) und [Verwenden von Bezeichnungen mit der goto\-Anweisung](assetId:///6cd7c31a-9822-4241-8566-f79f51be48fe).  
  
## Beispiel  
 In diesem Beispiel übergibt eine `goto`\-Anweisung das Steuerelement an den Punkt mit der Bezeichnung `stop`, wenn `i` gleich 3 ist.  
  
```  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
  **Äußere Schleife wird ausgeführt.  i \= 0**  
 **Innere Schleife wird ausgeführt.  j \= 0**  
 **Innere Schleife wird ausgeführt.  j \= 1**  
**Äußere Schleife wird ausgeführt.  i \= 1**  
 **Innere Schleife wird ausgeführt.  j \= 0**  
 **Innere Schleife wird ausgeführt.  j \= 1**  
**Äußere Schleife wird ausgeführt.  i \= 2**  
 **Innere Schleife wird ausgeführt.  j \= 0**  
 **Innere Schleife wird ausgeführt.  j \= 1**  
**Äußere Schleife wird ausgeführt.  i \= 3**  
 **Innere Schleife wird ausgeführt.  j \= 0**  
**Zur Beendigung gesprungen.  i \= 3**    
## Siehe auch  
 [Sprunganweisungen](../cpp/jump-statements-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)