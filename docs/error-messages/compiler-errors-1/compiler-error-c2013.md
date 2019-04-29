---
title: Compilerfehler C2013
ms.date: 11/04/2016
f1_keywords:
- C2013
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
ms.openlocfilehash: b279202b8b32197a99d230040207aa50bc100495
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351130"
---
# <a name="compiler-error-c2013"></a>Compilerfehler C2013

">" fehlt

In einer `#include` -Direktive fehlt eine schließende spitze Klammer. Fügen Sie die schließende Klammer hinzu, um den Fehler zu beheben.

Im folgenden Beispiel wird C2013 generiert:

```
// C2013.cpp
#include <stdio.h    // C2013
```

Mögliche Lösung:

```
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```