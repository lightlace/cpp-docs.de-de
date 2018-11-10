---
title: Speicherung von Bitfeldern
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 7aa6e02c347ff14bb0552320567b343c7215ebc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499085"
---
# <a name="storage-of-bit-fields"></a>Speicherung von Bitfeldern

**ANSI 3.5.2.1** Die Reihenfolge der Zuordnung von Bitfeldern in einem „int“

Bitfelder werden innerhalb einer Ganzzahl vom niedrigstwertigen hin zum höchstwertigen Bit angeordnet. Im folgenden Code etwa

```
struct mybitfields
{
   unsigned a : 4;
   unsigned b : 5;
   unsigned c : 7;
} test;

int main( void )
{
   test.a = 2;
   test.b = 31;
   test.c = 0;
}
```

wären die Bits folgendermaßen angeordnet:

```
00000001 11110010
cccccccb bbbbaaaa
```

Da die 80x86-Prozessoren das niedrige Byte ganzzahliger Werte vor dem hohen Byte speichern, wird die oben stehende Ganzzahl 0x01F2 im physischen Speicher als 0xF2 gefolgt von 0x01 gespeichert.

## <a name="see-also"></a>Siehe auch

[Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)