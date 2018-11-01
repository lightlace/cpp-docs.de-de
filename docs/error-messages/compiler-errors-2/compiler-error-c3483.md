---
title: Compilerfehler C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: c958eee234d25b008eb8cb03f40b45b8aaba81a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573458"
---
# <a name="compiler-error-c3483"></a>Compilerfehler C3483

"Variable" ist bereits Teil der Lambdaerfassungsliste.

Sie haben dieselbe Variable mehrmals an die Erfassungsliste eines Lambdaausdrucks übergeben.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie alle zusätzlichen Instanzen der Variablen aus der Erfassungsliste.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3483 generiert, da die Variable `n` mehrmals in der Erfassungsliste des Lambdaausdrucks vorkommt:

```
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)