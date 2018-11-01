---
title: Compilerfehler C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: f7327b7d2b0cc9fa4b617a9a6033116c43db6258
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528673"
---
# <a name="compiler-error-c2990"></a>Compilerfehler C2990

'Klasse': nichtklassentyp wurde bereits als Typ einer Klasse deklariert

Die nicht generische oder Vorlagenklasse definiert eine generische oder Vorlagenklasse-Klasse. Überprüfen Sie die Headerdateien für Konflikte.

Im folgende Beispiel wird die C2990 generiert:

```
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990 kann auch auftreten, wenn Generika verwendet werden:

```
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 kann auch aufgrund von eine wichtige Änderung in der Visual C++-Compiler für Visual C++ 2005 auftreten. der Compiler muss jetzt mehrere Deklarationen für den gleichen Typ Vorlagenspezifikation identisch sein.

Im folgende Beispiel wird die C2990 generiert:

```
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```