---
title: "Compilerfehler C2365"
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
  - "C2365"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2365"
ms.assetid: 35839b0b-4055-4b79-8957-b3a0871bdd02
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2365
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klassenmember": Erneute Definition; vorherige Definition war "Klassenmember"  
  
 Sie haben versucht, einen Klassenmember neu zu definieren.  
  
 Im folgenden Beispiel wird C2365 generiert.  
  
```  
// C2365.cpp // compile with: /c class C1 { int CFunc(); char *CFunc;   // C2365, already exists as a member function int CMem; char *CMem();   // C2365, already exists as a data member };  
```