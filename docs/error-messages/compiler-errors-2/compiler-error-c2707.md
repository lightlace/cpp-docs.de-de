---
title: Compiler-Fehler C2707 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2707
dev_langs:
- C++
helpviewer_keywords:
- C2707
ms.assetid: 3deaf45c-74da-4c9d-acc6-b82412720b74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdbd957bb1c19e28d08dd0fa5392eadd0f019756
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234055"
---
# <a name="compiler-error-c2707"></a>Compiler-Fehler C2707 generiert
'Bezeichner': Ungültiger Kontext für die systeminterne Funktion  
  
 Strukturierte Ausnahmebehandlung systeminternen Funktionen sind in bestimmten Kontexten ungültig:  
  
-   `_exception_code()` außerhalb eines Ausnahmefilters oder `__except` Block  
  
-   `_exception_info()` außerhalb eines Ausnahmefilters  
  
-   `_abnormal_termination()` außerhalb einer `__finally` Block  
  
 Um den Fehler zu beheben, achten Sie darauf, dass die Ausnahmebehandlung systeminternen Funktionen im entsprechenden Kontext platziert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2707 generiert.  
  
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