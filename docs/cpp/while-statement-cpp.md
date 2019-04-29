---
title: while-Anweisung (C++)
ms.date: 11/04/2016
f1_keywords:
- while_cpp
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
ms.openlocfilehash: 669618e9807109be18117968b1f5b6f49ec15e07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325415"
---
# <a name="while-statement-c"></a>while-Anweisung (C++)

Führt *Anweisung* solange wiederholt, bis *Ausdruck* zu NULL ausgewertet wird.

## <a name="syntax"></a>Syntax

```
while ( expression )
   statement
```

## <a name="remarks"></a>Hinweise

Der Test des *Ausdruck* erfolgt vor jeder Ausführung der Schleife; aus diesem Grund eine **während** Schleife NULL oder mehrmals ausgeführt. *Ausdruck* muss ein ganzzahliger Typ, ein Zeigertyp oder ein Klassentyp mit einer eindeutigen Konvertierung in einen Ganzzahl- oder Zeigertyp sein.

Ein **während** -Schleife kann auch beendet, wenn eine [Break](../cpp/break-statement-cpp.md), [Goto](../cpp/goto-statement-cpp.md), oder [zurückgeben](../cpp/return-statement-cpp.md) Text wird in der Anweisung ausgeführt. Verwendung [weiterhin](../cpp/continue-statement-cpp.md) beendet die aktuelle Iteration ohne Beenden der **während** Schleife. **weiterhin** übergibt die Steuerung an die nächste Iteration der **während** Schleife.

Der folgende code verwendet ein **während** Schleife gekürzt Unterstriche von einer Zeichenfolge:

```cpp
// while_statement.cpp

#include <string.h>
#include <stdio.h>
char *trim( char *szSource )
{
    char *pszEOS = 0;

    //  Set pointer to character before terminating NULL
    pszEOS = szSource + strlen( szSource ) - 1;

    //  iterate backwards until non '_' is found
    while( (pszEOS >= szSource) && (*pszEOS == '_') )
        *pszEOS-- = '\0';

    return szSource;
}
int main()
{
    char szbuf[] = "12345_____";

    printf_s("\nBefore trim: %s", szbuf);
    printf_s("\nAfter trim: %s\n", trim(szbuf));
}
```

Die Beendigungsbedingung wird am Anfang der Schleife ausgewertet. Solange keine nachgestellten Unterstriche vorhanden sind, wird die Schleife nicht ausgeführt.

## <a name="see-also"></a>Siehe auch

[Iterationsanweisungen](../cpp/iteration-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[do-while-Anweisung (C++)](../cpp/do-while-statement-cpp.md)<br/>
[for-Anweisung (C++)](../cpp/for-statement-cpp.md)<br/>
[Bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md)