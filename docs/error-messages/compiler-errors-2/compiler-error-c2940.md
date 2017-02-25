---
title: "Compilerfehler C2940 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2940"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2940"
ms.assetid: af6bf2bf-8de6-4cfd-bbf0-4c6b32a30edf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2940
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': Die Typklassen\-ID wurde als lokale typedef neu definiert  
  
 Eine generische oder Vorlagenklasse kann nicht als lokale `typedef` verwendet werden.  
  
 Im folgenden Beispiel wird C2940 generiert:  
  
```  
// C2940.cpp template<class T> struct TC {}; int main() { typedef int TC<int>;   // C2940 typedef int TC;   // OK }  
```  
  
 C2940 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2940b.cpp // compile with: /clr generic<class T> ref struct GC { }; int main() { typedef int GC<int>;   // C2940 typedef int GC; }  
```