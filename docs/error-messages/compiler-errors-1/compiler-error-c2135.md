---
title: "Compilerfehler C2135"
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
  - "C2135"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2135"
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2135
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bit operator': Ungültiger Bitfeldvorgang.  
  
 Der address\-of\-Operator \(`&`\) kann nicht auf ein Bitfeld angewendet werden.  
  
 Das folgende Beispiel generiert C2135:  
  
```  
// C2135.cpp struct S { int i : 1; }; struct T { int j; }; int main() { &S::i;   // C2135 address of a bit field &T::j;   // OK }  
```