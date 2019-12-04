---
title: Compilerfehler C3852
ms.date: 11/04/2016
f1_keywords:
- C3852
helpviewer_keywords:
- C3852
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
ms.openlocfilehash: f264333d802967d0350caa8ab4ba4925ffe019af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754874"
---
# <a name="compiler-error-c3852"></a>Compilerfehler C3852

' Member ' mit Typ ' type ': die Aggregat Initialisierung konnte diesen Member nicht initialisieren.

Es wurde versucht, eine Standard Initialisierung als Teil einer Aggregat Initialisierung zu einem Datenmember zuzuweisen, der in einer Aggregat Initialisierung keine Standard Initialisierung empfangen kann.

In den folgenden Beispielen wird C3852 generiert:

```cpp
// C3852.cpp
struct S
{
   short s;
};

struct S1
{
   int i;
   const S s;
};

struct S2
{
   int i;
   char & rc;
};

int main()
{
   S1 s1 = { 1 };   // C3852 const member
   // try the following line instead
   // S1 s1 = { 1, 2 };

   S2 s2 = { 2 };   // C3852 reference member
   // try the following line instead
   // char c = 'a';
   S2 s2 = { 2, c };
}
```
