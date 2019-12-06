---
title: Schwerwiegender ML-Fehler A1010
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 6ec82f7f6d559d977a9aa039ed91689a0ef4d49a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856877"
---
# <a name="ml-fatal-error-a1010"></a>Schwerwiegender ML-Fehler A1010

**fehlende Block Schachtelung:**

Ein Block Anfang hat kein entsprechendes Ende, oder für ein Block Ende war kein entsprechender Anfang vorhanden. Eine der folgenden Aktionen ist möglicherweise beteiligt:

- Eine Direktive auf hoher Ebene, z [. b. Wenn](../../assembler/masm/dot-if.md), [. Wiederholen](../../assembler/masm/dot-repeat.md)Sie oder [. Während](../../assembler/masm/dot-while.md).

- Eine bedingte Assemblydirektive, z. b. [if](../../assembler/masm/if-masm.md), [Repeat](../../assembler/masm/repeat.md)oder **while**.

- Eine Struktur-oder Union-Definition.

- Eine Prozedur Definition.

- Eine Segment Definition.

- Eine [POPCONTEXT](../../assembler/masm/popcontext.md) -Direktive.

- Eine bedingte Assemblydirektive, z. b. ein [else](../../assembler/masm/else-masm.md)-, [ElseIf](../../assembler/masm/elseif-masm.md)-oder **EndIf** -Direktive ohne übereinstimmendes [if](../../assembler/masm/if-masm.md).

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>