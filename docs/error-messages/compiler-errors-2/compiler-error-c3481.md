---
title: Compilerfehler C3481 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3481
dev_langs:
- C++
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25634bb455a032ceff51d5e35f7a16e00e020326
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066894"
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