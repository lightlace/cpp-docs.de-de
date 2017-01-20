---
title: "Compilerfehler C3397"
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
  - "C3397"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3397"
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3397
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Aggregatinitialisierung ist in Standardargumenten nicht zulässig.  
  
 Ein Array wurde falsch deklariert.  Weitere Informationen finden Sie unter [Arrays](../../windows/arrays-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3397 generiert.  
  
```  
// C3397.cpp // compile with: /clr // /clr /c void Func(array<int> ^p = gcnew array<int> { 1, 2, 3 });   // C3397 void Func2(array<int> ^p = gcnew array<int> (3));   // OK int main() { array<int> ^p = gcnew array<int> { 1, 2, 3};   // OK }  
```