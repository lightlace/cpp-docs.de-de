---
title: Nicht schwerwiegender ML-Fehler A2085
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 3bd89fb2b7f8b755cdb095e63ed89386332ecf9d
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855757"
---
# <a name="ml-nonfatal-error-a2085"></a>Nicht schwerwiegender ML-Fehler A2085

**Anweisung oder Register im aktuellen CPU-Modus nicht akzeptiert**

Es wurde versucht, eine Anweisung, ein Register oder ein Schlüsselwort zu verwenden, die für den aktuellen Prozessor Modus ungültig war.

Beispielsweise erfordern 32-Bit-Register [. 386](../../assembler/masm/dot-386.md) oder höher. Steuerelement Register wie CR0 erfordern den privilegierten Modus [. 386p](../../assembler/masm/dot-386p.md) oder höher. Dieser Fehler wird auch für die Schlüsselwörter **NEAR32**, **FAR32**und **Flat** generiert, die erfordern. **386** oder höher.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>