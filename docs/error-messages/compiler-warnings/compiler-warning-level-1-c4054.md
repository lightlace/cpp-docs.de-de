---
title: "Compilerwarnung (Stufe 1) C4054"
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
  - "C4054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4054"
ms.assetid: bdd7f6d5-f6f2-44a7-a013-39f309de7a29
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konvertierung': Von Funktionszeiger 'Typ1' zu Datenzeiger 'Typ2'.  
  
 Ein Funktionszeiger wird \(möglicherweise falsch\) in einen Datenzeiger umgewandelt. Dies ist unter „\/Za“ eine Warnung der Stufe 1 und unter „\/Ze“ eine Warnung der Stufe 4.  
  
 Im folgenden Beispiel wird C4054 generiert:  
  
```  
// C4054.c // compile with: /W1 /Za /c int (*pfunc)(); int* f() { return (int*)pfunc;   // C4054 }  
```  
  
 Unter „\/Ze“ ist dies eine Warnung der Stufe 4.  
  
```  
// C4054b.c // compile with: /W4 /c int (*pfunc)(); int* f() { return (int*)pfunc;   // C4054 }  
```