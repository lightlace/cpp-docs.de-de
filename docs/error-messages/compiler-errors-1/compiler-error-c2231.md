---
title: "Compilerfehler C2231"
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
  - "C2231"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2231"
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2231
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

".": Der linke Operand zeigt auf "Klassenschlüssel", verwenden Sie "–\>"  
  
 Der Operand auf der linken Seite des Vorgangs zur Memberauswahl \(.\) ist ein Zeiger und keine Klasse, Struktur oder Union.  
  
 Im folgenden Beispiel wird C2231 generiert:  
  
```  
// C2231.c struct S { int member; } s, *ps = &s; int main() { ps.member = 0;   // C2231 // OK ps->member = 0;   // crash s.member = 0; }  
```