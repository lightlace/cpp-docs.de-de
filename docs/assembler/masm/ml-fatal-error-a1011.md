---
title: Schwerwiegender ML-Fehler A1011
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 0d8d3896f7788aa3f51605651ee1b728b0e1d60a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856851"
---
# <a name="ml-fatal-error-a1011"></a>Schwerwiegender ML-Fehler A1011

**Direktive muss sich in einem Kontroll Block befinden**

Der Assembler hat eine Direktive auf hoher Ebene gefunden, die nicht erwartet wurde. Eine der folgenden Anweisungen wurde gefunden:

- [. ](../../assembler/masm/dot-else.md)Andernfalls ohne [. Wenn](../../assembler/masm/dot-if.md)

- [. Umdif](../../assembler/masm/dot-endif.md) ohne [. Wenn](../../assembler/masm/dot-if.md)

- [. Endw](../../assembler/masm/dot-endw.md) ohne [. Während](../../assembler/masm/dot-while.md)

- [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) ohne [. Wiederholen](../../assembler/masm/dot-repeat.md)

- [. Fahren](../../assembler/masm/dot-continue.md) Sie ohne fort [. Während](../../assembler/masm/dot-while.md) oder [. Wiederholen](../../assembler/masm/dot-repeat.md)

- [. ](../../assembler/masm/dot-break.md)Ohne Abbrechen [. Während](../../assembler/masm/dot-while.md) oder [. Wiederholen](../../assembler/masm/dot-repeat.md)

- [. Andernfalls folgt `.ELSE`](../../assembler/masm/dot-else.md)

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>