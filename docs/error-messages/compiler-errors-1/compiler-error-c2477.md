---
title: Compilerfehler C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: aa276ea839f11574609b183d78b46e08581a1b51
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743652"
---
# <a name="compiler-error-c2477"></a>Compilerfehler C2477

"Member": ein statischer Datenmember kann nicht über eine abgeleitete Klasse initialisiert werden.

Ein statischer Datenmember einer Vorlagen Klasse wurde nicht ordnungsgemäß initialisiert. Dies ist eine Breaking Change mit Versionen des Microsoft C++ -Compilers vor Visual Studio .NET 2003, um dem ISO C++ -Standard zu entsprechen.

Im folgenden Beispiel wird C2477 generiert:

```cpp
// C2477.cpp
// compile with: /Za /c
template <class T>
struct S {
   static int n;
};

struct X {};
struct A: S<X> {};

int A::n = 0;   // C2477

template<>
int S<X>::n = 0;
```
