---
title: Compilerfehler C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 1a61d4f2472ef6da8aedcf8a8ef90b70de47d8af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738270"
---
# <a name="compiler-error-c3495"></a>Compilerfehler C3495

'var': Eine Lambdaerfassung muss eine automatische Speicherdauer aufweisen.

Variablen, die keine automatische Speicherdauer aufweisen, etwa eine als `static` oder `extern`markierte Variable, können nicht erfasst werden.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Übergeben Sie keine `static` - oder `extern` -Variable an die Erfassungsliste des Lambdaausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3495 generiert, da die `static` -Variable `n` in der Erfassungsliste eines Lambda-Ausdrucks auftritt:

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)

