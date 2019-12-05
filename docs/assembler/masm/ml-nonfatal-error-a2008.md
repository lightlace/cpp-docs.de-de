---
title: Nicht schwerwiegender ML-Fehler A2008
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2008
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
ms.openlocfilehash: 192d82186a58d4e6b534ab5ec65b696d4d7ce3ee
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856752"
---
# <a name="ml-nonfatal-error-a2008"></a>Nicht schwerwiegender ML-Fehler A2008

**Syntax Fehler:**

Ein Token am aktuellen Speicherort hat einen Syntax Fehler verursacht.

Möglicherweise ist einer der folgenden Fehler aufgetreten:

- Ein Punkt Präfix wurde in einer-Direktive hinzugefügt oder weggelassen.

- Ein reserviertes Wort (z. **b. C** oder **size**) wurde als Bezeichner verwendet.

- Es wurde eine Anweisung verwendet, die bei der aktuellen Prozessor-oder Coprozessor-Auswahl nicht verfügbar war.

- Ein Vergleichs Lauf Zeit Operator (z. b. `==`) wurde in einer Bedingungs-Assemblyanweisung anstelle eines relationalen Operators (z. b. [EQ](../../assembler/masm/operator-eq.md)) verwendet.

- Eine Anweisung oder Direktive wurde zu wenig Operanden angegeben.

- Es wurde eine veraltete Direktive verwendet.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>