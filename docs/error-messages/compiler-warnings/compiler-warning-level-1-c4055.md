---
title: "Compilerwarnung (Stufe 1) C4055"
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
  - "C4055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4055"
ms.assetid: f04b13ca-88a7-4f2b-8065-42e73e5ac353
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konvertierung': Von Datenzeiger 'Typ1' zu Funktionszeiger 'Typ2'.  
  
 Ein Datenzeiger wird \(möglicherweise falsch\) in einen Funktionszeiger umgewandelt. Dies ist unter „\/Za“ eine Warnung der Stufe 1 und unter „\/Ze“ eine Warnung der Stufe 4.  
  
 Im folgenden Beispiel wird C4055 generiert:  
  
```  
// C4055.c // compile with: /Za /W1 /c typedef int (*PFUNC)(); int *pi; PFUNC f() { return (PFUNC)pi;   // C4055 }  
```  
  
 Unter „\/Ze“ ist dies eine Warnung der Stufe 4.  
  
```  
// C4055b.c // compile with: /W4 /c typedef int (*PFUNC)(); int *pi; PFUNC f() { return (PFUNC)pi;   // C4055 }  
```