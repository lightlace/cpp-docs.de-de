---
title: Verwendung eines Funktionsnamens ohne () kein Code generiert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13ca43386c9ef46f526538781a91fd1a81ade537
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710579"
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

[Codeoptimierung](../../build/reference/optimizing-your-code.md)