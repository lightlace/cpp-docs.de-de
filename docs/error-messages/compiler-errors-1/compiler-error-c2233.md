---
title: Compilerfehler C2233
ms.date: 11/04/2016
f1_keywords:
- C2233
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
ms.openlocfilehash: 7d96230f189a8f9371473d2da4df4e7be295ab03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499111"
---
# <a name="compiler-error-c2233"></a>Compilerfehler C2233

'Bezeichner': Arrays von Objekten, die Größe 0 (null) enthalten sind nicht zulässig

Jedes Objekt in einem Array muss mindestens ein Element enthalten.

Im folgende Beispiel wird die C2233 generiert:

```
// C2233.cpp
// compile with: /c
class A {
   char somearray[1];
};

class B {
   char zeroarray[];
};

A array[100];   // OK
B array2[100];   // C2233
```