---
title: Compilerfehler C3206 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3206
dev_langs:
- C++
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 62b23c33d1c2aada0e490cdf1dfe14e3abc6c713
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3206"></a>Compilerfehler C3206
„function“: Ungültiges Typargument für „param“, fehlende Typargumentliste für Klassentyp „typename“  
  
 Eine Vorlagenfunktion wurde so definiert, dass sie ein template-Typargument erwartet. Übergeben wurde aber ein template-Vorlagenargument.  
  
 Im folgenden Beispiel wird C3206 generiert:  
  
```  
// C3206.cpp  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S>();   // C3206  
   // try the following line instead  
   // f<S<int> >();  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C3206b.cpp  
// compile with: /c  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S<int> >();  
}  
```  
  
 C3206 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C3206c.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS>();   // C3206  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C3206d.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS<int> >();  
}  
```  
  
 Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Visual C++ 2005 .NET 2003 auftreten, wo Klassenvorlagen nicht als template-Typargument zulässig sind.  
  
 Eine Klassenvorlage ist nicht als template-Typargument zulässig. In Visual C++ .NET 2003 war dies erlaubt, aber in C++ ist es ungültig.  
  
 Das folgende Beispiel wird in Visual C++ .NET 2002 kompiliert, schlägt in Visual C++ .NET 2003 jedoch fehl:  
  
```  
// C3206e.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T<int> t;  
}  
  
int main() {  
   func<S>();   // C3206 S is not a type.  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C3206f.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T t;  
}  
  
int main() {  
   func<S<int> >();  
}  
```  
  
 Wenn ein template-Vorlagenparameter erforderlich ist und Sie eine Lösung benötigen, die für beide Versionen (Visual C++ .NET 2003- und Visual C++ .NET 2002) gilt, müssen Sie die Funktion in einer Vorlagenklasse umschließen, die einen template-Vorlagenparameter akzeptiert:  
  
```  
// C3206g.cpp  
template <class T>  
struct S {};  
  
template<template<class> class TT>  
struct X {  
   static void func() {  
      TT<int> t1;  
      TT<char> t2;  
   }  
};  
  
int main() {  
   X<S>::func();  
}  
```
