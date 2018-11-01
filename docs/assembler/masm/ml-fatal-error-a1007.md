---
title: Schwerwiegender ML-Fehler A1007
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 98933c3a24da22f447174a3b51c4855690aba83e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603397"
---
# <a name="ml-fatal-error-a1007"></a>Schwerwiegender ML-Fehler A1007

**Die Schachtelungsebene ist zu tief**

Der Assembler erreicht schachteln. Der Grenzwert beträgt 20 Ebenen außer vermerkt.

Eine der folgenden wurde zu tief geschachtelt:

- Eine allgemeine Richtlinie z. B. [. IF](../../assembler/masm/dot-if.md), [. Wiederholen Sie die](../../assembler/masm/dot-repeat.md), oder [. WÄHREND](../../assembler/masm/dot-while.md).

- Die Strukturdefinition einer.

- Eine bedingte-Assembly-Direktive.

- Die Definition einer Prozedur.

- Ein [PUSHCONTEXT](../../assembler/masm/pushcontext.md) Richtlinie (der Grenzwert ist 10).

- Eine Definition des Segments.

- Eine Includedatei.

- Ein Makro.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>