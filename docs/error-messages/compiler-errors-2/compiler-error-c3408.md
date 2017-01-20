---
title: "Compilerfehler C3408"
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
  - "C3408"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3408"
ms.assetid: 1f5ea979-fb1e-4214-b310-6fd6ca8249b1
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3408
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribut': Das Attribut ist für Vorlagendefinitionen nicht zulässig.  
  
 Attribute können nicht auf Vorlagendefinitionen angewendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3408 generiert:  
  
```  
// C3408.cpp // compile with: /c template <class T> struct PTS { enum { IsPointer = 0, IsPointerToDataMember = 0 }; }; template <class T> [coclass]   // C3408 struct PTS<T*> { enum { IsPointer = 1, IsPointerToDataMember = 0 }; }; template <class T, class U> struct PTS<T U::*> { enum { IsPointer = 1, IsPointerToDataMember = 1 }; }; struct S{}; extern "C" int printf(const char*,...); int main() { S s, *pS; int S::*ptm; printf("PTS<S>::IsPointer == %d PTS<S>::IsPointerToDataMember == %d\n", PTS<S>::IsPointer, PTS<S>:: IsPointerToDataMember); printf("PTS<S*>::IsPointer == %d PTS<S*>::IsPointerToDataMember == %d\n", PTS<S*>::IsPointer, PTS<S*>:: IsPointerToDataMember); printf("PTS<int S::*>::IsPointer == %d PTS<int S::*>::IsPointerToDataMember == %d\n", PTS<int S::*>::IsPointer, PTS<int S::*>:: IsPointerToDataMember); }  
```