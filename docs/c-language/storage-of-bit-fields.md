---
title: Speicherung von Bitfeldern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c39fa4455cfdc387ab5aa2068c80494a4a8810ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020084"
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