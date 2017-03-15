---
title: "Compilerfehler C2707 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2707"
ms.assetid: 3deaf45c-74da-4c9d-acc6-b82412720b74
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Falscher Kontext für systeminterne Funktion  
  
 Systeminterne Funktionen für die strukturierte Ausnahmebehandlung sind in bestimmten Kontexten unzulässig:  
  
-   `_exception_code()` außerhalb eines Ausnahmefilters oder eines `__except`\-Blockes  
  
-   `_exception_info()` außerhalb eines Ausnahmefilters  
  
-   `_abnormal_termination()` außerhalb eines `__finally`\-Blockes  
  
 Um den Fehler zu beheben, sollten Sie sicherstellen, dass systeminterne Funktionen für die Ausnahmebehandlung im richtigen Kontext verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2707 generiert.  
  
```  
// C2707.cpp  
#include <windows.h>  
#include <stdio.h>  
  
LONG MyFilter(LONG excode)   
{  
    return (excode == EXCEPTION_ACCESS_VIOLATION ?  
        EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);   // OK  
}  
  
LONG func(void)   
{  
    int x, y;  
    return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ?  // C2707  
             EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
  
    __try   
    {  
        y = 0;  
        x = 4 / y;  
        return 0;  
     }  
  
    __except(MyFilter(GetExceptionCode()))   
    {  
        return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ? // ok  
               EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
    }  
}  
  
int main()   
{  
    __try   
    {  
        func();  
    } __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf_s("Caught exception\n");  
    }  
}  
```