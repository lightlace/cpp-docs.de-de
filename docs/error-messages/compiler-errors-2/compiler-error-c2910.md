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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 202593b506fc957fb98cc390c1874312509ea481
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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