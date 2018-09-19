---
title: Schwerwiegender ML--Fehler A2008 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2008
dev_langs:
- C++
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 774cf4c2a51bf084fb63e572cc99b0c8e3cba26f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679374"
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