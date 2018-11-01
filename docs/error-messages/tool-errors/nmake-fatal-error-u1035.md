---
title: 'NMAKE: Schwerwiegender Fehler U1035'
ms.date: 11/04/2016
f1_keywords:
- U1035
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
ms.openlocfilehash: 9c4055bb99243f7d20c1da90aef7b916c46c2749
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589482"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE: Schwerwiegender Fehler U1035

Syntaxfehler: erwartet ':' oder '=' Trennzeichen

Entweder ein Doppelpunkt (**:**) oder ein Gleichheitszeichen (**=**) wurde erwartet.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Ein Doppelpunkt folgen kein Ziel.

1. Folgen ein Ziel mit einem Buchstaben, einem Doppelpunkt und ohne Leerzeichen (z. B. a:). NMAKE, die sie als eine Laufwerkangabe interpretiert.

1. Ein Doppelpunkt nicht auf eine Rückschlussregel folgen.

1. Eine Makrodefinition wurde nicht durch ein Gleichheitszeichen gefolgt.

1. Ein Zeichen gefolgt von einem umgekehrten Schrägstrich (**\\**), die zum Fortsetzen eines Befehls in eine neue Zeile verwendet wurde.

1. Eine Zeichenfolge angezeigt, die keine NMAKE Syntaxregel folgen.

1. Das Makefile wurde durch ein Textverarbeitungsprogramm formatiert.