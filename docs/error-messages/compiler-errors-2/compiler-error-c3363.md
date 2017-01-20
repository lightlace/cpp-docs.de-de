---
title: "Compilerfehler C3363"
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
  - "C3363"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3363"
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3363
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ" : "Typ\-ID" kann nur auf einen Typ angewendet werden.  
  
 Der [typeid](../../windows/typeid-cpp-component-extensions.md)\-Operator wurde falsch verwendet.  
  
## Beispiel  
 Im folgenden Beispiel wird C3363 generiert:  
  
```  
// C3363.cpp // compile with: /clr int main() { System::typeid;   // C3363 }  
```