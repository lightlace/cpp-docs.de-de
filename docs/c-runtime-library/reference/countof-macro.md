---
title: "_countof-Makro | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
  - "_countof"
  - "countof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_countof-Makro"
  - "countof-Makro"
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _countof-Makro
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnen Sie die Anzahl von Elementen in einem statisch zugeordneten Array.  
  
## Syntax  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### Parameter  
 `array`  
 Der Name eines Arrays.  
  
## Rückgabewert  
 Die Anzahl der Elemente im Array als `size_t` ausgedrückt.  
  
## Hinweise  
 Stellen Sie sicher, `array` tatsächlich ein Array ist, und kein Zeiger.  `_countof` erzeugt in C fehlerhafte Ergebnisse, wenn `array` ein Zeiger ist.  `_countof` generiert einen Kompilierungsfehler in C, wenn `array` ein Zeiger ist.  
  
## Anforderungen  
  
|Makro|Erforderlicher Header|  
|-----------|---------------------------|  
|`_countof`|\<stdlib.h\>|  
  
## Beispiel  
  
```  
// crt_countof.cpp  
#define _UNICODE  
#include <stdio.h>  
#include <stdlib.h>  
#include <tchar.h>  
  
int main( void )  
{  
   _TCHAR arr[20], *p;  
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );  
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );  
   // In C++, the following line would generate a compile-time error:  
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)  
  
   _tcscpy_s( arr, _countof(arr), _T("a string") );  
   // unlike sizeof, _countof works here for both narrow- and wide-character strings  
}  
```  
  
  **sizeof\(arr\) \= 40 bytes**  
**\_countof\(arr\) \= 20 elements**   
## Siehe auch  
 [sizeof\-Operator](../../cpp/sizeof-operator.md)