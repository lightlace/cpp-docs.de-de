---
title: "Compilerfehler C3375"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3375"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3375"
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3375
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Mehrdeutige Delegatfunktion.  
  
 Ein Delegat wurde möglicherweise als statische Memberfunktion oder ein ungebundener Delegat als Instanzfunktion instanziiert, daher hat der Compiler diesen Fehler ausgelöst.  
  
 Weitere Informationen finden Sie unter [delegate](../../windows/delegate-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3375 generiert:  
  
```  
// C3375.cpp // compile with: /clr ref struct R { static void f(R^) {} void f() {} }; delegate void Del(R^); int main() { Del ^ a = gcnew Del(&R::f);   // C3375 }  
```