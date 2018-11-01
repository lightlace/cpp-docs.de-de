---
title: Compilerfehler C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: c0075bf0e3749966a5e5b9fcd775b5d73171bf17
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599419"
---
# <a name="compiler-error-c3496"></a>Compilerfehler C3496

"this" wird immer nach Wert erfasst: "&" wird ignoriert.

Der `this`-Zeiger kann nicht als Verweis erfasst werden.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Erfassen Sie den `this` -Zeiger nach Wert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3496 generiert, weil ein Verweis auf den `this` -Zeiger in der Erfassungsliste eines Lambdaausdrucks auftritt:

```
// C3496.cpp
// compile with: /c

class C
{
   void f()
   {
      [&this] {}(); // C3496
   }
};
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)