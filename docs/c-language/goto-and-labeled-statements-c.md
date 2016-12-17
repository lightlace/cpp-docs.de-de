---
title: "goto und bezeichnete Anweisungen (C)"
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
  - "goto"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "goto-Schlüsselwort [C]"
  - "Anweisung mit Bezeichnung"
  - "Anweisungen, Mit Bezeichnung"
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# goto und bezeichnete Anweisungen (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Anweisung `goto` übertragt die Steuerung an eine Bezeichnung.  Die angegebene Bezeichnung muss sich in derselben Funktion befinden und kann nur vor einer Anweisung in derselben Funktion stehen.  
  
## Syntax  
 *statement*:  
 *labeled\-statement*  
  
 *jump\-statement*  
  
 *Sprunganweisung*:  
 **goto** *\-Bezeichner*  **;**  
  
 *labeled\-statement*:  
 *Bezeichner*  **:** *\-Anweisung*  
  
 Eine Anweisungsmarke ist nur für eine `goto`\-Anweisung sinnvoll. In jedem anderen Kontext wird eine bezeichnete Anweisung ohne Berücksichtigung der Bezeichnung ausgeführt.  
  
 Ein *jump\-statement* muss sich in derselben Funktion befinden und kann nur vor einer Anweisung in derselben Funktion stehen.  Der Satz der *Bezeichner*namen, die auf `goto` folgen, verfügt über einen eigenen Namespace, sodass die Namen nicht mit anderen Bezeichnern in Konflikt treten.  Bezeichnungen können nicht erneut deklariert werden.  Weitere Informationen finden Sie unter [Namespaces](../c-language/name-spaces.md).  
  
 Zur Programmierung empfiehlt es sich, die **break**\-, **continue**\- und `return`\-Anweisung der `goto`\-Anweisung vorzuziehen, wann immer dies möglich ist.  Da die **break**\-Anweisung nur eine Ebene der Schleife beendet, ist möglicherweise eine `goto`\-Anweisung erforderlich, um die Schleife aus einer tief verschachtelten Schleife heraus zu beenden.  
  
 In diesem Beispiel wird die `goto`\-Anweisung veranschaulicht.  
  
```  
// goto.c  
#include <stdio.h>  
  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 3; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 5 )  
                goto stop;  
        }  
    }  
  
    /* This message does not print: */  
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop: printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
 In diesem Beispiel übergibt eine `goto`\-Anweisung das Steuerelement an den Punkt mit der Bezeichnung `stop`, wenn `i` gleich 5 ist.  
  
## Siehe auch  
 [Anweisungen](../c-language/statements-c.md)