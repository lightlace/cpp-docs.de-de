---
title: Compilerfehler C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: 8492f108b57fbc63bd171276b1aa601f96a28b24
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754887"
---
# <a name="compiler-error-c3849"></a>Compilerfehler C3849

Funktions Stil Aufrufe für einen Ausdruck vom Typ "Typ" verlieren Konstante und/oder flüchtige Qualifizierer für alle verfügbaren Operator Überladungen.

Eine Variable mit einem angegebenen Konstanten Konstanten Typ kann nur Member-Funktionen aufzurufen, die mit denselben oder größeren Konstanten (konstant) definiert sind.

Um diesen Fehler zu beheben, stellen Sie eine entsprechende Member-Funktion bereit. Wenn die Konvertierung zu einem Qualifikations Verlust führt, können Sie keine Konvertierung für ein konstantenobjekt oder ein flüchtiges, flüchtiges Objekt ausführen. Sie können Qualifizierer gewinnen, aber keine Qualifizierer in einer Konvertierung verlieren.

In den folgenden Beispielen wird C3849 generiert:

```cpp
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```
