---
title: Compilerfehler C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: 1bbf9b269075717ae397b7d29ee28c278b1e4ec8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034938"
---
# <a name="compiler-error-c3493"></a>Compilerfehler C3493

"var" kann nicht implizit erfasst werden, da kein Standarderfassungsmodus angegeben wurde

Die leere Lambdaausdruckerfassung, `[]`, gibt an, dass der Lambdaausdruck weder explizit noch implizit Variablen erfasst.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Geben Sie einen Standarderfassungsmodus an, oder

- erfassen Sie explizit mindestens eine Variable.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3493 generiert, da eine externe Variable geändert, aber die leere Erfassungsklausel angegeben wird:

```
// C3493a.cpp

int main()
{
   int m = 55;
   [](int n) { m = n; }(99); // C3493
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3493 aufgelöst, indem die Erfassung nach Verweis als Standarderfassungsmodus angegeben wird.

```
// C3493b.cpp

int main()
{
   int m = 55;
   [&](int n) { m = n; }(99);
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)