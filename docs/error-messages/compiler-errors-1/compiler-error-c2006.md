---
title: Compilerfehler C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: 64f81929916cd3a4adf38a302ea34d46d9a5c070
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756551"
---
# <a name="compiler-error-c2006"></a>Compilerfehler C2006

' Direktive ' hat einen Dateinamen erwartet, ' Token ' gefunden.

Für Anweisungen wie [#include](../../preprocessor/hash-include-directive-c-cpp.md) oder [#Import](../../preprocessor/hash-import-directive-cpp.md) ist ein Dateiname erforderlich. Stellen Sie sicher, dass *Token* ein gültiger Dateiname ist, um den Fehler zu beheben. Fügen Sie auch den Dateinamen in doppelte Anführungszeichen oder eckige Klammern ein.

Im folgenden Beispiel wird C2006 generiert:

```cpp
// C2006.cpp
#include stdio.h   // C2006
```

Mögliche Lösung:

```cpp
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```
