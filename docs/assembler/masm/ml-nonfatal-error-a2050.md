---
title: Nicht schwerwiegender ML-Fehler A2050
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 15c6449ff4207c92dee28120d4f61be641cf01c8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856576"
---
# <a name="ml-nonfatal-error-a2050"></a>Nicht schwerwiegender ML-Fehler A2050

**"Real" oder "BCD" ist nicht zulässig.**

Eine Gleit Komma Zahl (Real) oder eine binäre cocd-Konstante (Binary Coded Decimal) wurde außer als dateninitialisierer verwendet.

Eine der folgenden Fehler ist aufgetreten:

- Eine reelle Zahl oder eine BCD wurde in einem Ausdruck verwendet.

- Eine reelle Zahl wurde verwendet, um eine andere Direktive als [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md)oder [TByte](../../assembler/masm/tbyte.md)zu initialisieren.

- Eine BCD wurde verwendet, um eine andere Direktive als `TBYTE`zu initialisieren.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>