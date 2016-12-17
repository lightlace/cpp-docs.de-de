---
title: "Compilerfehler C2148"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2148"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2148"
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2148
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gesamtgröße des Arrays darf 0x7fffffff Bytes nicht übersteigen  
  
 Ein Array überschreitet die zulässige Größe.  Verringern Sie die Größe des Arrays.  
  
## Beispiel  
 Im folgenden Beispiel wird C2148 generiert:  
  
```  
// C2148.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( ) {  
   char MyArray[0x7ffffffff];   // C2148  
   char * MyArray2 = (char *)malloc(0x7fffffff);  
  
   if (MyArray2)  
      printf_s("It worked!");  
   else  
      printf_s("It didn't work.");  
}  
```