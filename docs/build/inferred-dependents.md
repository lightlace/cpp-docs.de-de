---
title: Hergeleitete abhängige Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 958a33c29be0d68fee1044fff1d81235ea9370c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641375"
---
# <a name="inferred-dependents"></a>Hergeleitete abhängige Dateien

Eine hergeleitete abhängige stammt aus einer Rückschlussregel und ausgewertet wird, bevor der expliziten Abhängigkeiten. Wenn eine hergeleitete abhängige in Bezug auf sein Ziel veraltet ist, ruft NMAKE Befehlsblock für die Abhängigkeit. Wenn eine hergeleitete abhängige nicht vorhanden ist oder in Bezug auf seine eigenen Abhängigkeiten veraltet ist, aktualisiert die hergeleitete abhängige Datei zuerst. Weitere Informationen zu hergeleitete abhängige Dateien, finden Sie unter [Rückschlussregeln](../build/inference-rules.md).

## <a name="see-also"></a>Siehe auch

[Abhängige Dateien](../build/dependents.md)