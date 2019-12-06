---
title: Schwerwiegender ML-Fehler A1007
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 01633b4fa084b7d5e14af5a5c6e51e3dca684d2a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856916"
---
# <a name="ml-fatal-error-a1007"></a>Schwerwiegender ML-Fehler A1007

**Schachtelungs Ebene zu tief**

Der Assembler hat das Schachtelungs Limit erreicht. Der Grenzwert beträgt 20 Ebenen, außer wenn nichts anderes angegeben ist.

Eine der folgenden ist zu tief geschachtelt:

- Eine Direktive auf hoher Ebene, z [. b. Wenn](../../assembler/masm/dot-if.md), [. Wiederholen](../../assembler/masm/dot-repeat.md)Sie oder [. Während](../../assembler/masm/dot-while.md).

- Eine Struktur Definition.

- Eine Direktive für bedingte Assemblys.

- Eine Prozedur Definition.

- Eine [PUSHCONTEXT](../../assembler/masm/pushcontext.md) -Anweisung (das Limit ist 10).

- Eine Segment Definition.

- Eine Includedatei.

- Ein-Makro.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>