---
title: "Compilerfehler C2933"
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
  - "C2933"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2933"
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2933
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klasse": Typ\-Klassen\-ID neu definiert als typedef\-Member von "Bezeichner"  
  
 Eine generische oder Vorlagenklasse kann nicht als `typedef`\-Member verwendet werden.  
  
 Im folgenden Beispiel wird C2933 generiert:  
  
```  
// C2933.cpp // compile with: /c template<class T> struct TC { }; struct MyStruct { typedef int TC<int>;   // C2933 }; struct TC2 { }; struct MyStruct2 { typedef int TC2; };  
```  
  
 C2933 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2933b.cpp // compile with: /clr /c generic<class T> ref struct GC { }; struct MyStruct { typedef int GC<int>;   // C2933 }; ref struct GC2 { }; struct MyStruct2 { typedef int GC2; };  
```