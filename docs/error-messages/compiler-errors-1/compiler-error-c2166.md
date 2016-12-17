---
title: "Compilerfehler C2166"
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
  - "C2166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2166"
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L\-Wert gibt ein const\-Objekt an  
  
 Code versucht, ein als `const` deklariertes Element zu ändern.  
  
 Im folgenden Beispiel wird C2166 generiert:  
  
```  
// C2166.cpp int f(); int main() { ( (const int&) 1 ) = 5;   // C2166 }  
```