---
title: Compilerfehler C2450
ms.date: 11/04/2016
f1_keywords:
- C2450
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
ms.openlocfilehash: 3cbab274f8f7cd04d5fb86db69572e0b7fc1c04e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621803"
---
# <a name="compiler-error-c2450"></a>Compilerfehler C2450

Switch-Ausdruck vom Typ 'Typ' ist nicht zulässig

Die `switch` Ausdruck ausgewertet wird, auf einen ungültigen Typ. Es muss ausgewertet werden, ein ganzzahliger Typ oder ein Klassentyp mit eindeutige Konvertierung in einen Integer-Datentyp. Wenn er auf einen benutzerdefinierten Typ ausgewertet wird, müssen Sie einen Konvertierungsoperator angeben.

Im folgende Beispiel wird die C2450 generiert:

```
// C2450.cpp
class X {
public:
   int i;
} x;

class Y {
public:
   int i;
   operator int() { return i; }   // conversion operator
} y;

int main() {
   int j = 1;
   switch ( x ) {   // C2450, x is not type int
   // try the following line instead
   // switch ( y ) {
      default:  ;
   }
}
```