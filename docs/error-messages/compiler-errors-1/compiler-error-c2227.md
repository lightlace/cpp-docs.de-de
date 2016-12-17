---
title: "Compilerfehler C2227"
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
  - "C2227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2227"
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Links von „\-\>member“ muss sich ein Zeiger auf Klassen\-\/Struktur\-\/Union\-\/generischen Typ befinden.  
  
 Der Operand auf der linken Seite des `->` ist kein Zeiger auf eine Klasse, Struktur oder Union.  
  
 Das folgende Beispiel generiert C2227:  
  
```  
// C2227.cpp int *pInt; struct S { public: int member; } s, *pS = &s; int main() { pInt->member = 0;   // C2227 pInt points to an int pS->member = 0;   // OK }  
```