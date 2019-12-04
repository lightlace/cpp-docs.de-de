---
title: Compilerfehler C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 1c58c2d5da0049ec670e11c930b397caec3cbbee
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751520"
---
# <a name="compiler-error-c2990"></a>Compilerfehler C2990

"Class": nicht Klassentyp, wie bereits als Klassentyp deklariert

Die nicht generische oder Vorlagen Klasse definiert eine generische oder Vorlagen Klasse neu. Überprüfen Sie die Header Dateien auf Konflikte.

Im folgenden Beispiel wird C2990 generiert:

```cpp
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990 kann auch auftreten, wenn Generika verwendet werden:

```cpp
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 kann auch aufgrund einer Breaking Change im Microsoft C++ -Compiler für Visual Studio 2005 auftreten. der Compiler erfordert nun, dass mehrere Deklarationen für denselben Typ in Bezug auf die Vorlagen Spezifikation identisch sind.

Im folgenden Beispiel wird C2990 generiert:

```cpp
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
