---
title: Compilerfehler C2910 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2910
dev_langs:
- C++
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d726fffa61ed80352626df7a6f89467c420152bd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136126"
---
# <a name="compiler-error-c2910"></a>Compilerfehler C2910

'Funktion': kann nicht explizit spezialisiert werden

Der Compiler hat beim Versuch, eine Funktion explizit zweimal zu spezialisieren.

Im folgende Beispiel wird die C2910 generiert:

```
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

C2910 kann auch generiert werden, wenn Sie versuchen, ein nicht-Template-Element explizit spezialisiert werden kann. Sie können eine Funktionsvorlage, also nur explizit spezialisiert.

Im folgende Beispiel wird die C2910 generiert:

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

Dieser Fehler wird außerdem infolge einer konformitätsverbesserung für Compiler, die in Visual Studio .NET 2003 durchgeführt wurde generiert werden:.

Für Code in die Visual Studio .NET 2003 und Visual Studio .NET Version von Visual C++ gültig sein wird, entfernen Sie `template <>`.

Im folgende Beispiel wird die C2910 generiert:

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