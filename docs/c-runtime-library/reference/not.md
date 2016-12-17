---
title: "not"
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
  - "std::not"
  - "std.not"
  - "Not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "not-Funktion"
ms.assetid: d2ddbd5c-33c0-4aff-8961-feac155b4ba1
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# not
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Alternative zum \!\-Operator.  
  
## Syntax  
  
```  
  
#define not !  
  
```  
  
## Hinweise  
 Das Makro gibt den Operator \! aus.  
  
## Beispiel  
  
```  
// iso646_not.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 0;  
  
   if (!a)  
      cout << "a is zero" << endl;  
  
   if (not(a))  
      cout << "a is zero" << endl;  
}  
```  
  
  **a ist null**  
**a ist null**   
## Anforderungen  
 **Header:** \<iso646.h\>