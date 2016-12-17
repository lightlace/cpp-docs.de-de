---
title: "Compilerwarnung (Stufe 3) C4197"
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
  - "C4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4197"
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Flüchtige höchste Ebene bei Umwandlung wird ignoriert  
  
 Der Compiler hat eine Typumwandlung in einen mit [volatile](../../cpp/volatile-cpp.md) gekennzeichneten r\-Werttyp oder eine Typumwandlung eines r\-Werttyps in einen anderen, mit volatile gekennzeichneten Typ entdeckt.  Gemäß C\-Standard \(6.5.3\) sind Eigenschaften, die mit gekennzeichneten Typen verknüpft sind, nur für l\-Wertausdrücke von Bedeutung.  
  
 Im folgenden Beispiel wird C4197 generiert:  
  
```  
// C4197.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <signal.h>  
#include <stdlib.h>  
  
void sigproc(int);  
struct S  
{  
   int i;  
} s;  
  
int main()  
{  
   signal(SIGINT, sigproc);  
   s.i = 1;  
   S *pS = &s;  
   for ( ; (volatile int)pS->i ; )   // C4197  
      break;  
   // for ( ; *(volatile int *)&pS->i ; )   // OK  
   //    break;  
}  
  
void sigproc(int) // ctrl-C  
{  
   signal(SIGINT, sigproc);  
   s.i = 0;  
}  
  
```