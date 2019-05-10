---
title: Compilerfehler C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 73d8daa9576e4edc29958918c107e9edf18cc579
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447972"
---
# <a name="compiler-error-c2477"></a>Compilerfehler C2477

'Member': statische Datenmember kann nicht über eine abgeleitete Klasse initialisiert werden

Ein statischer Datenmember einer Vorlagenklasse wurde nicht ordnungsgemäß initialisiert. Dies ist eine wichtige Änderung in Versionen von Microsoft C++ Compiler vor Visual Studio .NET 2003, um die ISO-Datei entsprechen C++ standard.

Im folgende Beispiel wird es sich um C2477 generiert:

```
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