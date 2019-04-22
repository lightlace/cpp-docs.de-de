---
title: Compilerfehler C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: eff7c7a4f39524aa1d894b7b4590aa809714aae6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041201"
---
# <a name="compiler-error-c3481"></a>Compilerfehler C3481

'var': Es wurde keine Lambdaerfassungsvariable gefunden.

Der Compiler konnte die Definition einer Variablen, die Sie an die Erfassungsliste eines Lambda-Ausdrucks übergeben haben, nicht finden.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie die Variable aus der Erfassungsliste des Lambda-Ausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3481 generiert, weil die `n` -Variable nicht definiert ist:

```
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)