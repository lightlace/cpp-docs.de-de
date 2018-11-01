---
title: Nicht schwerwiegender ML-Fehler A2008
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2008
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
ms.openlocfilehash: 7f85a3aabb7b1955cede912168dfc04618b8f2b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630372"
---
# <a name="ml-nonfatal-error-a2008"></a>Nicht schwerwiegender ML-Fehler A2008

**Syntaxfehler:**

Ein Token an der aktuellen Position verursachte einen Syntaxfehler.

Eine der folgenden möglicherweise aufgetreten:

- Ein Punkt-Präfix wurde hinzugefügt oder in einer Anweisung ausgelassen.

- Ein reserviertes Wort (z. B. **C** oder **Größe**), die als Bezeichner verwendet wurde.

- Eine Anweisung wurde verwendet, die nicht mit der aktuellen Auswahl von Prozessoren oder -Coprozessor verfügbar war.

- Ein Laufzeit-Vergleichsoperator (z. B. `==`) wurde in einer bedingten Assembly-Anweisung, anstatt einen relationalen Operator verwendet (z. B. [EQ](../../assembler/masm/operator-eq.md)).

- Eine Anweisung oder die Richtlinie wurde nicht genügend Operanden angegeben.

- Es wurde eine veraltete-Direktive verwendet.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>