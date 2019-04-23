---
title: Compilerfehler C3487
ms.date: 11/04/2016
f1_keywords:
- C3487
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
ms.openlocfilehash: 01f8a1bd74ed2b7a3150afae5b46128c6f5b0ca2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028411"
---
# <a name="compiler-error-c3487"></a>Compilerfehler C3487

'return type': Alle Rückgabeausdrücke müssen in denselben Typ hergeleitet werden: Zuvor war es 'return type'.

Ein Lambdaausdruck muss seinen eigenen Rückgabetyp angeben, es sei denn, er enthält eine einzelne Rückgabeanweisung. Wenn ein Lambda-Ausdruck mehrere Rückgabeanweisungen enthält, müssen alle den gleichen Typ aufweisen.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Geben Sie einen nachgestellten Rückgabetyp für den Lambda-Ausdruck an. Stellen Sie sicher, dass alle Rückgaben vom Lambda denselben Typ aufweisen oder implizit zu diesem Rückgabetyp konvertiert werden können.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird „C3487“ generiert, da die Rückgabetypen vom Lambda nicht übereinstimmen.

```
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