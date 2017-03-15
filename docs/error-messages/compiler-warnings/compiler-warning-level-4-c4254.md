---
title: "Compilerwarnung (Stufe 4) C4254 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "c4254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4254"
ms.assetid: c7dcef24-d535-4c98-bb41-fc3d2b88fd11
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Umwandlung von 'Typ1' in 'Typ2', Datenverlust ist möglich  
  
 Ein größeres Bitfeld wurde einem kleineren Bitfeld zugewiesen.  Möglicherweise ist ein Datenverlust aufgetreten.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4254 generiert:  
  
```  
// C4254.cpp  
// compile with: /W4  
#pragma warning(default: 4254)  
  
struct X {  
   int a : 20;  
   int b : 12;  
};  
  
int main() {  
   X *x = new X();  
   x->b = 10;  
   x->a = 4;  
   x->a = x->b;    // OK  
   x->b = x->a;    // C4254  
};  
```