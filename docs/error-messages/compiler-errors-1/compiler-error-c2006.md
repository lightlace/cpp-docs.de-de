---
title: Compilerfehler C2006 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9468be17584a54047563bace2b35f5cb4888b41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031203"
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