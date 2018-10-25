---
title: Compilerfehler C3495 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3495
dev_langs:
- C++
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab2f92fd1d33d547bfe7703b71abe2797b37c8e6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070620"
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

