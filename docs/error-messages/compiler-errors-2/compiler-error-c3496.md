---
title: Compilerfehler C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 025498f3fe244916cd0a06e36feee6fdb532acc6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026691"
---
# <a name="compiler-error-c3496"></a>Compilerfehler C3496

"this" wird immer nach Wert erfasst: "&" wird ignoriert.

Der `this` -Zeiger kann nicht als Verweis erfasst werden.

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