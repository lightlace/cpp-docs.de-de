---
title: Unsachgemäßer Zugriff auf eine Union
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: a08f2c9aa76d0d2f2370dd45f9eb9ace77ceb76c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642953"
---
# <a name="improper-access-to-a-union"></a>Unsachgemäßer Zugriff auf eine Union

**ANSI 3.3.2.3** Auf ein Member eines union-Objekts wird mithilfe eines Members eines anderen Typs zugegriffen

Wenn eine Union von zwei Typen deklariert wird und ein Wert gespeichert ist, aber mit dem anderen Typ auf die Union zugegriffen wird, sind die Ergebnisse unzuverlässig.

Beispielsweise wird eine Union von **float** und `int` deklariert. Ein **float**-Wert wird gespeichert, aber später greift das Programm auf den Wert als `int` zu. In einer solchen Situation ist der Wert der internen Speicherung von **float**-Werten abhängig. Der Ganzzahlwert wäre nicht zuverlässig.

## <a name="see-also"></a>Siehe auch

[Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)