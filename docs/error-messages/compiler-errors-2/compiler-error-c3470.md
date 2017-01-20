---
title: "Compilerfehler C3470"
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
  - "C3470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3470"
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Eine Klasse kann nicht gleichzeitig einen Indexer \(indizierte Standardeigenschaft\) und einen \[\]\-Operator aufweisen.  
  
 Ein Typ kann nicht sowohl einen Standardindexer als auch einen \[\]\-Operator definieren.  
  
## Beispiel  
 Im folgenden Beispiel wird C3470 generiert:  
  
```  
// C3470.cpp // compile with: /clr using namespace System; ref class R { public: property int default[int] { int get(int i) { return i+1; } } int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470 }; int main() { R ^ r = gcnew R; // return r[9] + r["32"] - 42; }  
```