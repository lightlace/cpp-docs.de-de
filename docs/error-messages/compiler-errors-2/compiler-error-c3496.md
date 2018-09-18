---
title: Compilerfehler C3496 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ec4602e6a0061f5eb750ab29587209a6c97985d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062292"
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