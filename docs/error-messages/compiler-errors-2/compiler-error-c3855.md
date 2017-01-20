---
title: "Compilerfehler C3855"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3855"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3855"
ms.assetid: ed90f8c0-4154-4243-b066-493913df5727
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3855
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Typparameter 'param' ist mit der Deklaration nicht kompatibel  
  
 Der Compiler hat eine nontype\-Vorlage oder generische Parameter mit unterschiedlichen Namen gefunden.  Dieser Fehler kann auftreten, wenn ein angegebener Vorlagenparameter in der Definition einer Vorlagenspezialisierung mit seiner Deklaration nicht kompatibel ist.  
  
 Im folgenden Beispiel wird C3855 generiert:  
  
```  
// C3855.cpp  
template <int N>  
struct C {  
   void f();  
};  
  
template <char N>  
void C<N>::f() {}   // C3855  
```  
  
 Mögliche Lösung:  
  
```  
// C3855b.cpp  
// compile with: /c  
template <int N>  
struct C {  
   void f();  
};  
  
template <int N>  
void C<N>::f() {}  
```  
  
 C3855 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C3855c.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC1 {  
   generic <class U>  
   ref struct GC2;  
};  
  
generic <class T>  
generic <class U>  
generic <class V>  
ref struct GC1<T>::GC2 { };   // C3855  
```  
  
 Mögliche Lösung:  
  
```  
// C3855d.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC1 {  
   generic <class U>  
   ref struct GC2;  
};  
  
generic <class T>  
generic <class U>  
ref struct GC1<T>::GC2 { };  
```