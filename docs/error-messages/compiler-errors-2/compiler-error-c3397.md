---
title: "Compilerfehler C3397 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3397"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3397"
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
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