---
title: Signierte bitweise Operationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184fd5a0e6c12cb58e9fed759459e7b8172896f8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038294"
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