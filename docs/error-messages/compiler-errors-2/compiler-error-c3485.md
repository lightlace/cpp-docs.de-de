---
title: "Compilerfehler C3485"
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
  - "C3485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3485"
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Lambdadefinition kann keine CV\-Qualifizierer aufweisen.  
  
 Sie können keinen `const`\- oder `volatile`\-Qualifizierer als Teil der Definition eines Lambda\-Ausdrucks verwenden.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `const`\- oder `volatile`\-Qualifizierer aus der Definition des Lambda\-Ausdrucks.  
  
## Beispiel  
 Im folgenden Beispiel wird C3485 erzeugt, weil der `const`\-Qualifizierer als Teil der Definition eines Lambda\-Ausdrucks verwendet wird:  
  
```  
// C3485.cpp int main() { auto x = []() const mutable {}; // C3485 }  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)