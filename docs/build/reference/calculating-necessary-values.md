---
title: Berechnen der erforderlichen Werte
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
ms.openlocfilehash: 80c028a315669fb0032628bb86a834d429935f50
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513866"
---
# <a name="calculating-necessary-values"></a>Berechnen der erforderlichen Werte

Zwei wichtige Kategorien von Informationen durch die Verzögerung Hilfsroutine berechnet werden müssen. Zu diesem Zweck stehen zwei Inlinefunktionen in delayhlp.cpp zur Berechnung dieser Informationen.

- Die erste berechnet den Index des aktuellen Imports in den drei verschiedenen Tabellen (Address-Tabelle (IAT) und gebundene Importadresstabelle (BIAT) ungebundenen Importadresstabelle (UIAT)).

- Die zweite zählt die Anzahl der Importe in eine gültige IAT.

```cpp
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="see-also"></a>Siehe auch

[Die Hilfsfunktion](understanding-the-helper-function.md)