---
title: Nicht schwerwiegender ML-Fehler A2050
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 59d08b9c2743a3b45633527bcc54b3e1c4d6a58c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439714"
---
# <a name="ml-nonfatal-error-a2050"></a>Nicht schwerwiegender ML-Fehler A2050

**Real oder BCD-Anzahl, die nicht zulässig**

Eine Gleitkommazahl (tatsächlichen) oder die Binary Coded Decimal (BCD)-Konstante wurde als verwendet als dateninitialisierer.

Eine der folgenden aufgetreten ist:

- Eine reelle Zahl oder einen BCD wurde in einem Ausdruck verwendet.

- Eine reelle Zahl wurde verwendet, um eine Direktive außer initialisieren [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), oder [TBYTE](../../assembler/masm/tbyte.md).

- Einen BCD wurde verwendet, um eine Direktive außer initialisieren `TBYTE`.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>