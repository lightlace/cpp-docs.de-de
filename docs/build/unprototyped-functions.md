---
title: Funktionen ohne Prototyp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c030bd99fc185b3c52535aecb45697672ef4c14
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717677"
---
# <a name="unprototyped-functions"></a>Funktionen ohne Prototyp

Für Funktionen, die nicht vollständige Prototypen wird der Aufrufer die ganzzahlige Werte als ganze Zahlen und Gleitkommazahlen-Punktwerte als mit doppelter Genauigkeit übergeben. Nur Gleitkommawerte enthält sowohl ganzzahligen Register die Gleitkommaregister den Float-Wert und für den Fall, dass der aufgerufene den Wert in die Ganzzahlregister erwartet.

```
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)