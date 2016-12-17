---
title: "Compilerwarnung (Stufe 3) C4645"
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
  - "C4645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4645"
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Funktion, die mit "\_\_declspec\(noreturn\)" deklariert wurde, hat eine Rückgabeanweisung  
  
 Eine [return](../../cpp/return-statement-in-program-termination-cpp.md)\-Anweisung wurde in einer Funktion gefunden, die mit dem [noreturn](../../cpp/noreturn.md) `__declspec`\-Modifizierer gekennzeichnet ist. Die `return`\-Anweisung wurde ignoriert.  
  
 Im folgenden Beispiel wird C4645 generiert:  
  
```  
// C4645.cpp // compile with:  /W3 void __declspec(noreturn) func() { return;   // C4645, delete this line to resolve } int main() { }  
```