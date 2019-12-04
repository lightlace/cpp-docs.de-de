---
title: Compilerfehler C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: 0061a7171dd08440ec5d8c8b8cadb77303ff8f41
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761114"
---
# <a name="compiler-error-c2910"></a>Compilerfehler C2910

"Function": kann nicht explizit spezialisiert werden.

Der Compiler hat einen Versuch erkannt, eine Funktion zweimal explizit zu spezialisieren.

Im folgenden Beispiel wird C2910 generiert:

```cpp
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

C2910 kann auch generiert werden, wenn Sie versuchen, einen nicht-Vorlagen Member explizit zu spezialisieren. Das heißt, Sie können eine Funktions Vorlage nur explizit spezialisieren.

Im folgenden Beispiel wird C2910 generiert:

```cpp
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

Dieser Fehler wird auch aufgrund von compilerübereinstimmungs-Aufgaben generiert, die in Visual Studio .NET 2003 ausgeführt wurden:.

Wenn Code in Visual Studio .NET 2003 und Visual Studio .NET-Versionen von Visual C++Studio gültig ist, entfernen Sie `template <>`.

Im folgenden Beispiel wird C2910 generiert:

```cpp
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
