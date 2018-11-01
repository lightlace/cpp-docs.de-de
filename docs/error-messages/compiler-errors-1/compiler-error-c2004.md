---
title: Compilerfehler C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: fb100d977188cd3a7d5b0ebbb3e29b53942871dc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452007"
---
# <a name="compiler-error-c2004"></a>Compilerfehler C2004

"defined(id)" erwartet

Ein Bezeichner muss in den Klammern hinter dem Präprozessorschlüsselwort angegeben werden.

Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual Visual Studio .NET 2003 auftreten: fehlende Klammer in Präprozessordirektive. Wenn die schließende Klammer in einer Präprozessordirektive fehlt, generiert der Compiler einen Fehler.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2004 generiert.

```
// C2004.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG   // C2004
        printf_s("DEBUG defined\n");
    #endif
}
```

## <a name="example"></a>Beispiel

Mögliche Lösung:

```
// C2004b.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG)
        printf_s("DEBUG defined\n");
    #endif
}
```