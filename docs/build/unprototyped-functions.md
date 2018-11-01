---
title: Funktionen ohne Prototyp
ms.date: 11/04/2016
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
ms.openlocfilehash: 38207be6111dadc338593e55b683b88e0480e1ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633427"
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