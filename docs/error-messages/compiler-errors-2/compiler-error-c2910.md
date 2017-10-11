---
title: Compilerfehler C2910 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2910
dev_langs:
- C++
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: db1c4d7b4533d6bbfb0848c1dc16a7336ad81eb0
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2910"></a>Compilerfehler C2910
'Funktion': kann nicht explizit spezialisiert werden kann  
  
 Der Compiler hat einen Versuch, eine Funktion zweimal explizit zu spezialisieren.  
  
 Im folgende Beispiel wird C2910 generiert:  
  
```  
// C2910.cpp  
// compile with: /c  
template <class T>  
struct S;  
  
template <> struct S<int> { void f() {} };  
template <> void S<int>::f() {}   // C2910 delete this specialization  
```  
  
 C2910 kann auch generiert werden, wenn Sie versuchen, ein Element nicht von der Vorlage explizit spezialisiert. Eine Funktionsvorlage kann also nur explizit spezialisiert werden.  
  
 Im folgende Beispiel wird C2910 generiert:  
  
```  
// C2910b.cpp  
// compile with: /c  
template <class T> struct A {  
   A(T* p);  
};  
  
template <> struct A<void> {  
   A(void* p);  
};  
  
template <class T>  
inline A<T>::A(T* p) {}  
  
template <> A<void>::A(void* p){}   // C2910  
// try the following line instead  
// A<void>::A(void* p){}  
```  
  
 Dieser Fehler wird außerdem infolge einer konformitätsverbesserung, die in Visual Studio .NET 2003 durchgeführt wurde generiert werden:.  
  
 Für Code in der Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig sein wird, entfernen Sie `template <>`.  
  
 Im folgende Beispiel wird C2910 generiert:  
  
```  
// C2910c.cpp  
// compile with: /c  
template <class T> class A {  
   void f();  
};  
  
template <> class A<int> {  
   void f();  
};  
  
template <> void A<int>::f() {}   // C2910  
// try the following line instead  
// void A<int>::f(){}   // OK  
```
