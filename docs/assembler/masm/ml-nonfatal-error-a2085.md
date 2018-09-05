---
title: Schwerwiegender ML--Fehler A2085 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd5ec9f36a4f956b8eeb097b6a8f8eaed89ba2b2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681435"
---
# <a name="ml-nonfatal-error-a2085"></a>Nicht schwerwiegender ML-Fehler A2085

**-Anweisung oder die Registrierung, die im aktuellen CPU-Modus nicht akzeptiert.**

Es wurde versucht, eine Anweisung, Register oder Schlüsselwort, das für den aktuellen Prozessormodus ungültig war.

Beispielsweise erfordern von 32-Bit-Register [.386](../../assembler/masm/dot-386.md) oder höher. Steuerelement registriert werden, wie z. B. CR0 erfordern privilegierten Modus [.386P](../../assembler/masm/dot-386p.md) oder höher. Dieser Fehler wird auch generiert werden, für die **NEAR32**, **FAR32**, und **Flatfile** Schlüsselwörter, die erforderlich sind. **386** oder höher.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>