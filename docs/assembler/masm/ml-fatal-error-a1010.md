---
title: ML-Schwerwiegender Fehler A1010 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12b7e8698951e8ef59e0433134ec992af5d5f77f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676296"
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