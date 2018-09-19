---
title: Compilerfehler C3498 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb87abc113e586aa4f3097444df4c5a46a6a92c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106771"
---
# <a name="compiler-error-c3498"></a>Compilerfehler C3498

'Var': eine Variable mit einer verwalteten oder WinRTtype kann nicht erfasst

Sie können keine Variable erfassen, die einen verwalteten Typ oder einen Windows-Runtime-Typ in einem „lambda“ aufweist.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Übergeben Sie die verwaltete oder Windows-Runtime-Variable an die Parameterliste des Lambdaausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3498 generiert, da eine Variable mit einem verwalteten Typ in der Erfassungsliste eines Lambdaausdrucks angezeigt wird:

```
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3498 durch Übergeben der verwaltete Variablen `s` an die Parameterliste des Lambda-Ausdrucks aufgelöst:

```
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)