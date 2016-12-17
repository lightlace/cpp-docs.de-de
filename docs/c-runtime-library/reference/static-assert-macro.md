---
title: "_STATIC_ASSERT-Makro"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_STATIC_ASSERT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_STATIC_ASSERT-Makro"
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# _STATIC_ASSERT-Makro
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Werten Sie einen Ausdruck zur Kompilierzeit ausgeführt und generieren Sie einen Fehler, wenn das Ergebnis `FALSE` ist.  
  
## Syntax  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### Parameter  
 `booleanExpression`  
 Ausdruck \(einschließlich Zeiger\) bis der Wert ungleich 0 \(null\) \(`TRUE`\) oder 0 ergibt \(`FALSE`\).  
  
## Hinweise  
 Dieses Makro entspricht [\_ASSERT und \_ASSERTE Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), außer dass `booleanExpression` wird zur Kompilierzeit statt zur Laufzeit ausgewertet.  Wenn `booleanExpression` auf `FALSE` \(0\) ergibt, wird [Compilerfehler C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) generiert.  
  
## Beispiel  
 In diesem Beispiel untersuchen wir, dass `sizeof` größer als `int` ist, oder gleich 2 Bytes und ob `sizeof``long` 1 Byte ist.  Das Programm wird nicht kompiliert und sie generiert [Compilerfehler C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md), da `long` größer als 1 Byte ist.  
  
```  
// crt__static_assert.c  
  
#include <crtdbg.h>  
#include <stdio.h>  
  
_STATIC_ASSERT(sizeof(int) >= 2);  
_STATIC_ASSERT(sizeof(long) == 1);  // C2466  
  
int main()  
{  
    printf("I am sure that sizeof(int) will be >= 2: %d\n",  
        sizeof(int));  
    printf("I am not so sure that sizeof(long) == 1: %d\n",  
        sizeof(long));  
}  
```  
  
## Anforderungen  
  
|Makro|Erforderlicher Header|  
|-----------|---------------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h\>|  
  
## .NET Framework-Entsprechung  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [\_ASSERT\-, \_ASSERTE\-, \_ASSERT\_EXPR\-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)