---
title: Compilerfehler C3855 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3855
dev_langs:
- C++
helpviewer_keywords:
- C3855
ms.assetid: ed90f8c0-4154-4243-b066-493913df5727
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d30731f291ff881f6d2012177e247360a1dd810
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3855"></a>Compilerfehler C3855
'Klasse': Typparameter "Param" ist nicht kompatibel mit der Deklaration  
  
 Der Compiler hat Nichttyp-Vorlage oder die generische Parameter mit unterschiedlichen Namen gefunden. Dies kann auftreten, wenn ein angegebene Vorlagenparameter in der Definition einer Spezialisierung einer Klassenvorlage mit der Deklaration nicht kompatibel ist.  
  
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