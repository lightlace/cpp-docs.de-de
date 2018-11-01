---
title: Compilerfehler C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 7c16ffa37f4d7192956afae26c825b63add1bfdd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540246"
---
# <a name="compiler-error-c3412"></a>Compilerfehler C3412

'Template': die Vorlage im aktuellen Bereich kann nicht spezialisiert

Eine Vorlage kann nicht im Gültigkeitsbereich der Klasse, sondern nur im globalen oder im Namespace-Gültigkeitsbereich spezialisiert werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3412 generiert.

```
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine mögliche Lösung.

```
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```