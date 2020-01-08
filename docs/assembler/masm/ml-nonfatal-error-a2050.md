---
title: Nicht schwerwiegender ML-Fehler A2050
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 311aedd0cc739fd862efb0a18cc444b3fb75b165
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316979"
---
# <a name="ml-nonfatal-error-a2050"></a>Nicht schwerwiegender ML-Fehler A2050

**"Real" oder "BCD" ist nicht zulässig.**

Eine Gleit Komma Zahl (Real) oder eine binäre cocd-Konstante (Binary Coded Decimal) wurde außer als dateninitialisierer verwendet.

Eine der folgenden Fehler ist aufgetreten:

- Eine reelle Zahl oder eine BCD wurde in einem Ausdruck verwendet.

- Eine reelle Zahl wurde verwendet, um eine andere Direktive als [DWORD](dword.md), [QWORD](qword.md)oder [TByte](tbyte.md)zu initialisieren.

- Eine BCD wurde verwendet, um eine andere Direktive als `TBYTE`zu initialisieren.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](ml-error-messages.md)
