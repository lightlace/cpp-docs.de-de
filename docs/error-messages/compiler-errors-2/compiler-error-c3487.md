---
title: Compilerfehler C3487
ms.date: 11/04/2016
f1_keywords:
- C3487
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
ms.openlocfilehash: 7b38755470e3746066711382b2ed471badc8e197
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738439"
---
# <a name="compiler-error-c3487"></a>Compilerfehler C3487

'return type': Alle Rückgabeausdrücke müssen in denselben Typ hergeleitet werden: Zuvor war es 'return type'.

Ein Lambdaausdruck muss seinen eigenen Rückgabetyp angeben, es sei denn, er enthält eine einzelne Rückgabeanweisung. Wenn ein Lambda-Ausdruck mehrere Rückgabeanweisungen enthält, müssen alle den gleichen Typ aufweisen.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Geben Sie einen nachgestellten Rückgabetyp für den Lambda-Ausdruck an. Stellen Sie sicher, dass alle Rückgaben vom Lambda denselben Typ aufweisen oder implizit zu diesem Rückgabetyp konvertiert werden können.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird „C3487“ generiert, da die Rückgabetypen vom Lambda nicht übereinstimmen.

```cpp
// C3487.cpp
// Compile by using: cl /c /W4 C3487.cpp

int* test(int* pi) {
   // To fix the error, uncomment the trailing return type below
   auto odd_pointer = [=]() /* -> int* */ {
      if (*pi % 2)
         return pi;
      return nullptr; // C3487 - nullptr is not an int* type
   };
   return odd_pointer();
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
