---
title: Compilerfehler C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: c23f17483925f25468214165fb459db577e576fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475087"
---
# <a name="compiler-error-c2006"></a>Compilerfehler C2006

'Direktive': Dateinamen erwartet, aber 'token' gefunden

Anweisungen wie z. B. [#include](../../preprocessor/hash-include-directive-c-cpp.md) oder [#import](../../preprocessor/hash-import-directive-cpp.md) ist ein Dateiname erforderlich. Um den Fehler zu beheben, stellen Sie sicher, dass *token* ist ein gültiger Dateiname. Darüber hinaus sollten Sie den Dateinamen in doppelte Anführungszeichen oder Klammern.

Im folgende Beispiel wird die C2006 generiert:

```
// C2006.cpp
#include stdio.h   // C2006
```

Mögliche Lösung:

```
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```