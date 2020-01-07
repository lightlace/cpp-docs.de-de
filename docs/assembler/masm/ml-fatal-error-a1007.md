---
title: Schwerwiegender ML-Fehler A1007
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: c9527769e0d9397de90f49cbce98b2cca42bed50
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317122"
---
# <a name="ml-fatal-error-a1007"></a>Schwerwiegender ML-Fehler A1007

**Schachtelungs Ebene zu tief**

Der Assembler hat das Schachtelungs Limit erreicht. Der Grenzwert beträgt 20 Ebenen, außer wenn nichts anderes angegeben ist.

Eine der folgenden ist zu tief geschachtelt:

- Eine Direktive auf hoher Ebene, z [. b. Wenn](dot-if.md), [. Wiederholen](dot-repeat.md)Sie oder [. Während](dot-while.md).

- Eine Struktur Definition.

- Eine Direktive für bedingte Assemblys.

- Eine Prozedur Definition.

- Eine [PUSHCONTEXT](pushcontext.md) -Anweisung (das Limit ist 10).

- Eine Segment Definition.

- Eine Includedatei.

- Ein-Makro.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](ml-error-messages.md)
