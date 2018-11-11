---
title: Signierte bitweise Operationen
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: d178900a25a5d7a080068fb1919fcba2853bef14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652009"
---
# <a name="signed-bitwise-operations"></a>Signierte bitweise Operationen

**ANSI 3.3** Die Ergebnisse der bitweisen Vorgänge an Ganzzahlen mit Vorzeichen

Bitweise Vorgänge auf Ganzzahlen mit Vorzeichen arbeiten genauso wie bitweise Vorgänge auf Ganzzahlen ohne Vorzeichen. So kann beispielsweise `-16 & 99` binär ausgedrückt werden als

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Das Ergebnis des bitweisen AND-Vorgangs ist 96.

## <a name="see-also"></a>Siehe auch

[Ganze Zahlen](../c-language/integers.md)