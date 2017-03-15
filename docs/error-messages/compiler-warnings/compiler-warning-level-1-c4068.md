---
title: "Compilerwarnung (Stufe 1) C4068 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4068"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4068"
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4068
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unbekanntes Pragma  
  
 Der Compiler hat ein nicht erkanntes [Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) ignoriert. Stellen Sie sicher, dass das **Pragma** vom verwendeten Compiler zugelassen wird. Im folgenden Beispiel wird C4068 generiert:  
  
```  
// C4068.cpp // compile with: /W1 #pragma NotAValidPragmaName   // C4068, use valid name to resolve int main() { }  
```