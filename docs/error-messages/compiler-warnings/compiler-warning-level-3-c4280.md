---
title: "Compilerwarnung (Stufe 3) C4280 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4280"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4280"
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 3) C4280
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator \-\>' wurde durch den Typ "Typ" selbstrekursiv  
  
 Der Code hat zugelassen, dass der **operator–\>** sich selbst aufruft.  
  
 Im folgenden Beispiel wird C4280 generiert:  
  
```  
// C4280.cpp  
// compile with: /W3 /WX  
struct A  
{  
   int z;  
   A& operator ->();  
};  
  
void f(A y)  
{  
   int i = y->z; // C4280  
}  
```