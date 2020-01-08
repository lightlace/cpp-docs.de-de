---
title: Schwerwiegender ML-Fehler A1011
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 5607d6d56e0b3889332dcf2624d519529819b1c9
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318076"
---
# <a name="ml-fatal-error-a1011"></a>Schwerwiegender ML-Fehler A1011

**Direktive muss sich in einem Kontroll Block befinden**

Der Assembler hat eine Direktive auf hoher Ebene gefunden, die nicht erwartet wurde. Eine der folgenden Anweisungen wurde gefunden:

- [. ](dot-else.md)Andernfalls ohne [. Wenn](dot-if.md)

- [. Umdif](dot-endif.md) ohne [. Wenn](dot-if.md)

- [. Endw](dot-endw.md) ohne [. Während](dot-while.md)

- [. UNTILCXZ](dot-untilcxz.md) ohne [. Wiederholen](dot-repeat.md)

- [. Fahren](dot-continue.md) Sie ohne fort [. Während](dot-while.md) oder [. Wiederholen](dot-repeat.md)

- [. ](dot-break.md)Ohne Abbrechen [. Während](dot-while.md) oder [. Wiederholen](dot-repeat.md)

- [. Andernfalls folgt `.ELSE`](dot-else.md)

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](ml-error-messages.md)
