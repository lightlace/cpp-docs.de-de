---
title: "Compilerfehler C2942"
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
  - "C2942"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2942"
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2942
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klasse": "Typ\-Klasse\-ID" wird als formales Argument einer Funktion neu definiert.  
  
 Eine generische oder Vorlagenklasse kann nicht als formales Argument verwendet werden. Ein Argument kann nicht direkt an den Konstruktor einer generischen oder Vorlagenklasse übergeben werden.  
  
 Im folgenden Beispiel wird C2942 generiert.  
  
```  
  
// C2942.cpp // compile with: /c template<class T> struct TC {}; void f(int TC<int>) {}   // C2942 // OK struct TC2 {}; void f(TC2 i) {}  
```  
  
 C2942 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2942b.cpp // compile with: /clr /c generic<class T> ref struct GC {}; void f(int GC<int>) {}   // C2942 ref struct GC2 { }; void f(int GC2) {}  
```