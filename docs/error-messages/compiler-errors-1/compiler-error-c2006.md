---
title: Compilerfehler C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: c23f17483925f25468214165fb459db577e576fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209002"
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