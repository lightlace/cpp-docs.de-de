---
title: Nicht schwerwiegender ML-Fehler A2085
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: f8fdedfc1bc8bff63124d18fe1410d9f144cb926
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316836"
---
# <a name="ml-nonfatal-error-a2085"></a>Nicht schwerwiegender ML-Fehler A2085

**Anweisung oder Register im aktuellen CPU-Modus nicht akzeptiert**

Es wurde versucht, eine Anweisung, ein Register oder ein Schlüsselwort zu verwenden, die für den aktuellen Prozessor Modus ungültig war.

Beispielsweise erfordern 32-Bit-Register [. 386](dot-386.md) oder höher. Steuerelement Register wie CR0 erfordern den privilegierten Modus [. 386p](dot-386p.md) oder höher. Dieser Fehler wird auch für die Schlüsselwörter **NEAR32**, **FAR32**und **Flat** generiert, die erfordern. **386** oder höher.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](ml-error-messages.md)
