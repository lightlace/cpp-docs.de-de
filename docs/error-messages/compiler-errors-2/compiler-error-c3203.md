---
title: Compilerfehler C3203
ms.date: 11/04/2016
f1_keywords:
- C3203
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
ms.openlocfilehash: 1d0ed5ec717efecb9fbea4a9451836c0471522b6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738712"
---
# <a name="compiler-error-c3203"></a>Compilerfehler C3203

'type': nicht spezialisierte Klassenvorlage oder generisch kann nicht als Vorlage oder generisches Argument für die Vorlage oder den generischen Parameter 'Param' verwendet werden; ein realer Typ wurde erwartet

Sie übergeben ein ungültiges Argument an eine Klassenvorlage oder generische Vorlage. Die Klassenvorlage oder generische Vorlage erwartet einen Typ als Parameter.

Dieser Fehler kann als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio 2005 durchgeführt wurde: eine nicht spezialisierte Klassen Vorlage kann nicht als Vorlagen Argument in einer Basisklassen Liste verwendet werden. Um C3203 zu beheben, fügen Sie explizit Typparametervorlage(n) zum Vorlagenklassennamen hinzu, wenn dieser als Vorlagenparameter in einer Basisklassenliste verwendet wird.

```cpp
// C3203.cpp
template< typename T >
struct X {
   void f(X) {}
};

template< typename T >
struct Y : public X<Y> {   // C3203
// try the following line instead
// struct Y : public X<Y<T> > {
   void f(Y) {}
};

int main() {
   Y<int> y;
}
```

Im folgenden Beispiel wird C3203 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3203_b.cpp
// compile with: /c
template <class T>
struct S1 {};

template <class T>
class C1 {};

typedef C1<S1> MyC1;   // C3203

// OK
template <template <class> class T>
class C2 {};

typedef C2<S1> MyC1;

template <class T>
class C3 {};

typedef C3<S1<int> > MyC12;
```

C3203 kann auch auftreten, wenn Generics verwendet werden:

```cpp
// C3203_c.cpp
// compile with: /clr /c
generic <class T>
value struct GS1 {};

generic <class T>
value struct GC1 {};

typedef GC1<GS1> MyGC1;   // C3203
typedef GC1<GS1<int> > MyGC2;   // OK
```
