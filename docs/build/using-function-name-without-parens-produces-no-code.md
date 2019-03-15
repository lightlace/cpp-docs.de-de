---
title: Bei Verwendung eines Funktionsnamens ohne "()" wird kein Code generiert
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 51be77dc8f4fe072ea6cc46dd51e38862649feda
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826000"
---
# <a name="using-function-name-without--produces-no-code"></a>Bei Verwendung eines Funktionsnamens ohne "()" wird kein Code generiert

Wenn Sie den Namen einer Funktion deklariert, die in Ihrem Programm ohne Klammern verwendet wird, erzeugt der Compiler keinen Code. Dies geschieht unabhängig davon, ob die Funktion Parameter akzeptiert, da der Compiler die Adresse der Funktion berechnet werden soll; Da es sich bei der Funktionsaufruf-Operator "()" nicht vorhanden ist, ist jedoch kein Aufruf vorgenommen. Das Ergebnis ist ähnlich der folgenden:

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

In Visual C++ generiert das selbst bei Verwendung von Warnstufe 4 keine diagnostische Ausgabe. Es wird keine Warnung ausgegeben; Es wird kein Code erstellt.

Der folgende Beispielcode (mit einer Warnmeldung) kompiliert und verknüpft ordnungsgemäß ohne Fehler jedoch wird kein Code auf generiert `funcn( )`. Damit dies ordnungsgemäß funktioniert fügen Sie den Funktionsaufruf-Operator "()" hinzu.

```
#include <stdio.h>
void funcn();

int main() {
   funcn;      /* missing function call operator;
                  call will fail.  Use funcn() */
   }

void funcn() {
   printf("\nHello World\n");
}
```

## <a name="see-also"></a>Siehe auch

[Codeoptimierung](optimizing-your-code.md)
