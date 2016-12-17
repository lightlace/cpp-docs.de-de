---
title: "Compilerfehler C3400"
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
  - "C3400"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3400"
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3400
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zirkuläre Einschränkungsabhängigkeit mit „constraint\_1“ und „constraint\_2“  
  
 Der Compiler hat zirkuläre Einschränkungen erkannt.  
  
 Weitere Informationen finden Sie unter [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3400 generiert:  
  
```  
// C3400.cpp // compile with: /clr /c generic<class T, class U> where T : U where U : T   // C3400 public ref struct R {};  
```