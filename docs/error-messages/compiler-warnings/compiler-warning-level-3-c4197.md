---
title: Compilerwarnung (Stufe 3) C4197 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4197
dev_langs: C++
helpviewer_keywords: C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaa66b3d1effe1afd6adbe3a70b82ab98e162569
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4197"></a>Compilerwarnung (Stufe 3) C4197 generiert
'Typ': der obersten Ebene Volatile in Typumwandlung wird ignoriert.  
  
 Der Compiler hat eine Typumwandlung in einem mit gekennzeichneten [volatile](../../cpp/volatile-cpp.md), oder eine Typumwandlung eines r-Wert-Typs zu einem Typ, der mit Volatile qualifiziert wird. Gemäß den C-standard (6.5.3) sind gekennzeichneten Typen zugeordnete Eigenschaften nur für die l-Wertausdrücke von Bedeutung.  
  
 Im folgende Beispiel wird C4197 generiert:  
  
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