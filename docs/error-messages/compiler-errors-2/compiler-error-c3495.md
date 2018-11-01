---
title: Compilerfehler C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 81fcbb8102d5df8059aad00772b7ee0cc07c01d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452467"
---
# <a name="compiler-error-c3495"></a>Compilerfehler C3495

'var': Eine Lambdaerfassung muss eine automatische Speicherdauer aufweisen.

Variablen, die keine automatische Speicherdauer aufweisen, etwa eine als `static` oder `extern`markierte Variable, können nicht erfasst werden.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Übergeben Sie keine `static` - oder `extern` -Variable an die Erfassungsliste des Lambdaausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3495 generiert, da die `static` -Variable `n` in der Erfassungsliste eines Lambda-Ausdrucks auftritt:

```
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)

