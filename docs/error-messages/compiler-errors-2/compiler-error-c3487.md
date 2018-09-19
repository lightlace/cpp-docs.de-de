---
title: Compilerfehler C3487 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3487
dev_langs:
- C++
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acd0dad31a565b9e75741e3a66a5d48dfedec69f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087109"
---
# <a name="compiler-error-c3487"></a>Compilerfehler C3487

„Rückgabetyp“: Alle Rückgabeausdrücke müssen in denselben Typ hergeleitet werden: Zuvor war es „Rückgabetyp“.

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