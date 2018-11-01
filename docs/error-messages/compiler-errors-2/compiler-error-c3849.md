---
title: Compilerfehler C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: ec6725472d31b0b2ade0cd73da4440036239fde3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598561"
---
# <a name="compiler-error-c3849"></a>Compilerfehler C3849

Funktion-Style-Aufruf an ein Ausdruck vom Typ 'Typ' verlieren const- und/oder volatile-Qualifizierer für alle Anzahl verfügbaren operatorüberladungen

Eine Variable mit einem angegebenen Const-Volatile-Typ kann nur Member mit dieselbe oder eine höhere Const-Volatile-Qualifikationen definierten Funktionen aufrufen.

Um diesen Fehler zu beheben, geben Sie eine entsprechenden Member-Funktion. Sie können keine Konvertierung in ein Const oder volatile qualifiziertes Objekt ausführen, wenn die Konvertierung zu einer Qualifikation führt. Der Qualifizierer darf, jedoch nicht Qualifizierer in einer Konvertierung.

In den folgenden Beispielen C3849 generiert:

```
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