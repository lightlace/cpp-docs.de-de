---
title: "Compilerfehler C3298"
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
  - "C3298"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3298"
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3298
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"constraint\_1": "constraint\_2" kann nicht als Einschränkung verwendet werden, da "constraint\_2" die ref\-Einschränkung und "constraint\_1" die Werteinschränkung aufweist.  
  
 Sie können keine sich gegenseitig ausschließende Eigenschaften für eine Einschränkung angeben. Beispielsweise kann ein generischer Typparameter nicht gleichzeitig auf einen Werttyp und einen Referenztyp eingeschränkt werden.  
  
 Weitere Informationen finden Sie unter [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3298 generiert:  
  
```  
// C3298.cpp // compile with: /clr /c generic<class T, class U> where T : ref class where U : T, value class   // C3298 public ref struct R {};  
```