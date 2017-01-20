---
title: "Compilerfehler C2952"
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
  - "C2952"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2952"
ms.assetid: a40e18a2-d02c-4511-854f-6c6fd6789a1a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2952
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„declaration“: Typdeklaration enthält keine Vorlagenparameterliste.  
  
 Eine Vorlagendeklaration wurde nicht ordnungsgemäß formatiert.  
  
 Im folgenden Beispiel wird C2952 generiert:  
  
```  
// C2952.cpp // compile with: /c template <class T> struct S { template <class T1> struct S1 { void f(); }; }; template <class T> void S<T>::S1<T>::f() {}   // C2952 // OK template <class T> template <class T1> void S<T>::S1<T1>::f() {}  
```  
  
 C2952 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2952b.cpp // compile with: /clr /c generic <class T> ref struct GC { generic <class T1> ref struct GC1 { void f(); }; }; generic <class T> void GC<T>::GC1<T>::f() {}   // C2952 // OK generic <class T> generic <class T1> void GC<T>::GC1<T1>::f() {}  
```