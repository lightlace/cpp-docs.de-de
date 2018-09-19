---
title: Compilerfehler C3206 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3206
dev_langs:
- C++
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa7775f0da26846851677aa267b91438ce84dbf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117958"
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


Eine Klassenvorlage ist nicht als template-Typargument zulässig. Im folgende Beispiel löst C3206 aus:

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

Wenn ein Template-Vorlagenparameter erforderlich ist, müssen Sie die Funktion in einer Vorlagenklasse umschließen, die einen Template Template-Parameter akzeptiert:

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