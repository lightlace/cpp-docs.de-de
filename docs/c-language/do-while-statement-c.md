---
title: do-while-Anweisung (C)
ms.date: 11/04/2016
f1_keywords:
- do
- while
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
ms.openlocfilehash: 052b02beca49f5de19c6f68cc475edb5f5daf6e2
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147502"
---
# <a name="do-while-statement-c"></a>do-while-Anweisung (C)

Mit der *do-while*-Anweisung wird eine Anweisung oder ein Anweisungsblock wiederholt ausgeführt, bis ein bestimmter Ausdruck den Wert „false“ liefert.

## <a name="syntax"></a>Syntax

*iteration-statement*: &nbsp;&nbsp;&nbsp;&nbsp;**do** *Anweisung* **while (** *Ausdruck* **) ;**

Der *Ausdruck* in einer *do-while*-Anweisung wird ausgewertet, nachdem der Text der Schleife ausgeführt wird. Daher wird der Text der Schleife immer mindestens einmal ausgeführt.

Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen. Die Ausführung erfolgt folgendermaßen:

1. Der Anweisungstext wird ausgeführt.

1. Danach wird *expression*, der Ausdruck, ausgewertet. Wenn der *Ausdruck* „false“ ist, wird die *do-while*-Anweisung beendet und die Steuerung an die nächste Anweisung im Programm weitergegeben. Wenn *expression* „true“ (ungleich 0 [null]) ist, wird der Prozess wiederholt, beginnend mit Schritt 1.

Die *do-while*-Anweisung kann auch beendet werden, wenn eine **break**-, **goto**- oder **return**-Anweisung innerhalb des Anweisungstexts ausgeführt wird.

In diesem Beispiel wird die *do-while*-Anweisung veranschaulicht:

```C
do
{
    y = f( x );
    x--;
} while ( x > 0 );
```

In dieser *do-while*-Anweisung werden die beiden Anweisungen `y = f( x );` und `x--;` unabhängig vom Anfangswert von `x` ausgeführt. Anschließend wird `x > 0` ausgewertet. Wenn `x` größer als 0 ist, wird der Anweisungstext noch einmal ausgeführt und `x > 0` erneut ausgewertet. Der Anweisungstext wird wiederholt ausgeführt, solange `x` größer als 0 ist. Die Ausführung der *do-while*-Anweisung wird beendet, wenn `x` 0 oder negativ ist. Der Text der Schleife wird mindestens einmal ausgeführt.

## <a name="see-also"></a>Siehe auch

[do-while-Anweisung (C++)](../cpp/do-while-statement-cpp.md)
