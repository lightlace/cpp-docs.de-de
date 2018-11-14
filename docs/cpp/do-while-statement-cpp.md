---
title: do-while-Anweisung (C++)
ms.date: 11/04/2016
f1_keywords:
- do_cpp
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
ms.openlocfilehash: d930c1884975288ff11f4d4e5cf2728e717e17d5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326666"
---
# <a name="do-while-statement-c"></a>do-while-Anweisung (C++)

Führt eine *Anweisung* solange wiederholt, bis die angegebene beendigungsbedingung (der *Ausdruck*) zu NULL ausgewertet wird.

## <a name="syntax"></a>Syntax

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>Hinweise

Der Test der beendigungsbedingung wird nach jeder Ausführung der Schleife wird. aus diesem Grund eine **sind – während** Schleife ausgeführt wird, einmal oder mehrmals, abhängig vom Wert des beendigungsausdrucks. Die **do-while**-Anweisung kann auch beendet werden, wenn eine [break](../cpp/break-statement-cpp.md)-, [goto](../cpp/goto-statement-cpp.md)- oder [return](../cpp/return-statement-cpp.md)-Anweisung innerhalb des Anweisungstexts ausgeführt wird.

Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen. Die Ausführung erfolgt folgendermaßen:

1. Der Anweisungstext wird ausgeführt.

1. Danach wird *expression*, der Ausdruck, ausgewertet. Wenn der *Ausdruck* „false“ ist, wird die **do-while**-Anweisung beendet und die Steuerung an die nächste Anweisung im Programm weitergegeben. Wenn *expression* „true“ (ungleich 0 [null]) ist, wird der Prozess wiederholt, beginnend mit Schritt 1.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die **sind – während** Anweisung:

```cpp
// do_while_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        printf_s("\n%d",i++);
    } while (i < 3);
}
```

## <a name="see-also"></a>Siehe auch

[Iterationsanweisungen](../cpp/iteration-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[while-Anweisung (C++)](../cpp/while-statement-cpp.md)<br/>
[for-Anweisung (C++)](../cpp/for-statement-cpp.md)<br/>
[Bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md)