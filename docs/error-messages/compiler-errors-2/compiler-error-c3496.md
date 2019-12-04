---
title: Compilerfehler C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: b9542f1904c6797a77c88c88a37aff9348364268
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738179"
---
# <a name="compiler-error-c3496"></a>Compilerfehler C3496

"this" wird immer nach Wert erfasst: "&" wird ignoriert.

Der `this` -Zeiger kann nicht als Verweis erfasst werden.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Erfassen Sie den `this` -Zeiger nach Wert.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3496 generiert, weil ein Verweis auf den `this` -Zeiger in der Erfassungsliste eines Lambdaausdrucks auftritt:

```cpp
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
