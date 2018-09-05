---
title: Schwerwiegender ML--Fehler A2050 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd2e0e6c2fc818ef9286fd303c07a26bdd8b4e5a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680670"
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