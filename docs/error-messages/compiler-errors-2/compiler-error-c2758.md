---
title: Compilerfehler C2758
ms.date: 11/04/2016
f1_keywords:
- C2758
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
ms.openlocfilehash: c3a86b8b8c7f122929a52221d4f01a17c50395be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618031"
---
# <a name="compiler-error-c2758"></a>Compilerfehler C2758

'member': Ein Member eines Verweistyps muss initialisiert werden

Der Compilerfehler C2758 wird ausgelöst, wenn der Konstruktor ein Member des Verweistyps in einer Initialisiererliste nicht initialisiert. Der Compiler lässt das Member undefiniert. Verweismembervariablen müssen initialisiert werden, wenn sie deklariert werden, oder sie müssen einen Wert in der Initialisierungsliste des Konstruktors erhalten.

Im folgenden Beispiel wird C2758 generiert:

```
// C2758.cpp
// Compile by using: cl /W3 /c C2758.cpp
struct A {
   const int i;

   A(int n) { };   // C2758
   // try the following line instead
   // A(int n) : i{n} {};
};
```