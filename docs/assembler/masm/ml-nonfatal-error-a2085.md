---
title: Nicht schwerwiegender ML-Fehler A2085
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 729f6f38761171c6ddc4cccfc2443c6a2b597bf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444358"
---
# <a name="ml-nonfatal-error-a2085"></a>Nicht schwerwiegender ML-Fehler A2085

**-Anweisung oder die Registrierung, die im aktuellen CPU-Modus nicht akzeptiert.**

Es wurde versucht, eine Anweisung, Register oder Schlüsselwort, das für den aktuellen Prozessormodus ungültig war.

Beispielsweise erfordern von 32-Bit-Register [.386](../../assembler/masm/dot-386.md) oder höher. Steuerelement registriert werden, wie z. B. CR0 erfordern privilegierten Modus [.386P](../../assembler/masm/dot-386p.md) oder höher. Dieser Fehler wird auch generiert werden, für die **NEAR32**, **FAR32**, und **Flatfile** Schlüsselwörter, die erforderlich sind. **386** oder höher.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>