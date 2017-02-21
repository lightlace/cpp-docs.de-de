---
title: "Compilerwarnung (Stufe 1) C4313 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4313"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4313"
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 1) C4313
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Funktion“: „Formatbezeichner“ in der Formatzeichenfolge steht mit der Argumentennummer vom Typ „Typ“ in Konflikt.  
  
 Es besteht ein Konflikt zwischen dem angegebenen Format und dem Wert, den Sie übergeben.  Beispielsweise haben Sie einen 64\-Bit\-Parameter an einen nicht qualifizierten Formatbezeichner „%d“ übergeben, wohingegen ein 32\-Bit\-Ganzzahl\-Parameter erwartet wird.  Diese Warnung ist nur aktiv, wenn der Code für 64\-Bit\-Ziele kompiliert wird.  
  
## Beispiel  
 Im folgenden Codebeispiel wird C4313 generiert, wenn dies für 64\-Bit\-Ziele kompiliert wird.  
  
```  
// C4313.cpp  
// Compile by using: cl /W1 C4313.cpp  
#include <stdio.h>  
int main() {  
   int * pI = 0;  
   printf("%d", pI);   // C4313 on 64-bit platform code  
   // Try one of the following lines instead:  
   // printf("%p\n", pI);  
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information  
}  
```