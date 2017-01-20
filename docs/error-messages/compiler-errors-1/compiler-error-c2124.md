---
title: "Compilerfehler C2124"
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
  - "C2124"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2124"
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2124
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Division oder Modulo durch Null  
  
 Ein konstanter Ausdruck hat einen Nenner 0. Um den Fehler zu beheben, vermeiden Sie die Division durch null.  
  
 Im folgenden Beispiel wird C2124 generiert:  
  
```  
// C2124.cpp int main() { int i = 1 / 0;   // C2124  do not divide by zero int i2 = 12 / 2;   // OK }  
```