---
title: Compilerfehler C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 16c111a0fb8608615abaee495680fa38920b6c77
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447347"
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

C2990 kann auch auftreten, aufgrund von eine wichtige Änderung in der Microsoft C++ Compiler für Visual Studio 2005; der Compiler muss jetzt mehrere Deklarationen für den gleichen Typ Vorlagenspezifikation identisch sein.

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