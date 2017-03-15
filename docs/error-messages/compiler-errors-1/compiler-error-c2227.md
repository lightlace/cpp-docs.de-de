---
title: "Compilerfehler C2227 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2227"
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Links von „\-\>member“ muss sich ein Zeiger auf Klassen\-\/Struktur\-\/Union\-\/generischen Typ befinden.  
  
 Der Operand auf der linken Seite des `->` ist kein Zeiger auf eine Klasse, Struktur oder Union.  
  
 Das folgende Beispiel generiert C2227:  
  
```  
// C2227.cpp int *pInt; struct S { public: int member; } s, *pS = &s; int main() { pInt->member = 0;   // C2227 pInt points to an int pS->member = 0;   // OK }  
```