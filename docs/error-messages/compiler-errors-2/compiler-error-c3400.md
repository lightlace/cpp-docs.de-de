---
title: "Compilerfehler C3400 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3400"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3400"
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
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