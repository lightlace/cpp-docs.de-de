---
title: Compilerfehler C3849 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3849
dev_langs:
- C++
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08f89deb3bd83162dd7cf5dc80335e5274efa1c7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077502"
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