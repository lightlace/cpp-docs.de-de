---
title: Compilerfehler C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 7c16ffa37f4d7192956afae26c825b63add1bfdd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173456"
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