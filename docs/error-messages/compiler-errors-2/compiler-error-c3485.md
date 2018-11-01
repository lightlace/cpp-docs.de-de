---
title: Compilerfehler C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 09080a402767835cda9711c2f0fc4d7c8d787439
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508020"
---
# <a name="compiler-error-c3485"></a>Compilerfehler C3485

Eine Lambdadefinition kann keine CV-Qualifizierer aufweisen.

Sie können keinen `const` - oder `volatile` -Qualifizierer als Teil der Definition eines Lambda-Ausdrucks verwenden.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie den `const` - oder `volatile` -Qualifizierer aus der Definition des Lambda-Ausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3485 erzeugt, weil der `const` -Qualifizierer als Teil der Definition eines Lambda-Ausdrucks verwendet wird:

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)