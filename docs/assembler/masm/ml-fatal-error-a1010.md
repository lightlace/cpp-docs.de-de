---
title: Schwerwiegender ML-Fehler A1010
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: eb4d77b856e93a8d64ee6c51bec63ceae59b22e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449126"
---
# <a name="ml-fatal-error-a1010"></a>Schwerwiegender ML-Fehler A1010

**nicht übereinstimmende Block schachteln:**

Eine Block beginnt verfügte nicht über ein zugehöriges End oder ein Block End verfügte nicht über eine übereinstimmende beginnt. Eine der folgenden möglicherweise beteiligt:

- Eine allgemeine Richtlinie z. B. [. IF](../../assembler/masm/dot-if.md), [. Wiederholen Sie die](../../assembler/masm/dot-repeat.md), oder [. WÄHREND](../../assembler/masm/dot-while.md).

- Eine bedingte-Assembly-Anweisung, wie z. B. [IF](../../assembler/masm/if-masm.md), [wiederholen](../../assembler/masm/repeat.md), oder **während**.

- Eine Struktur oder Union-Definition.

- Die Definition einer Prozedur.

- Eine Definition des Segments.

- Ein [POPCONTEXT](../../assembler/masm/popcontext.md) Richtlinie.

- Eine bedingte-Assembly, z. B. die Richtlinie ein [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), oder **ENDIF** ohne ein entsprechendes [IF](../../assembler/masm/if-masm.md).

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>