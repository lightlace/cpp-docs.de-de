---
title: Rückschlussregeln
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
ms.openlocfilehash: cb67fc8fe8e65814c9b169f7936c7d225d26e1e3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471044"
---
# <a name="inference-rules"></a>Rückschlussregeln

Rückschlussregeln Geben Sie Befehle zum Aktualisieren von Zielen und abhängigen Elemente für Ziele abzuleiten. Erweiterungen in einer Rückschlussregel entspricht ein einzelnes Ziel, und abhängig, die den gleichen Basisnamen aufweisen. Rückschlussregeln werden die benutzerdefinierten oder vordefinierten; Vordefinierte Regeln können neu definiert werden.

Wenn eine veraltete Abhängigkeit keine Befehle, und wenn [. SUFFIXE](../build/dot-directives.md) enthält die Erweiterung der abhängigen, NMAKE verwendet, die eine Regel, deren Erweiterungen übereinstimmen, das Ziel und eine vorhandene, Datei im aktuellen oder angegebenen Verzeichnis. Wenn mehr als eine Regel vorhandene Dateien entspricht der **. SUFFIXE** Liste bestimmt, welche verwenden; Liste Priorität abgeleitet von links nach rechts. Wenn eine abhängige Datei nicht vorhanden ist und nicht als Ziel in einem anderen Beschreibungsblock aufgelistet ist, kann eine Rückschlussregel fehlenden abhängigen aus einer anderen Datei mit den gleichen Basisnamen erstellen. Wenn eine Beschreibung des Blocks Ziel keine abhängigen Dateien oder Befehle verfügt, kann eine Rückschlussregel das Ziel aktualisieren. Rückschlussregeln können ein Befehlszeilen-Ziel erstellen, selbst wenn keine Beschreibungsblock vorhanden ist. NMAKE: kann eine Regel für eine hergeleitete abhängige aufrufen, auch wenn eine explizite abhängige angegeben wird.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Definieren einer Regel](../build/defining-a-rule.md)

[Stapelverarbeitungsregeln](../build/batch-mode-rules.md)

[Vordefinierte Regeln](../build/predefined-rules.md)

[Hergeleitete abhängige Dateien und Regeln](../build/inferred-dependents-and-rules.md)

[Vorrang in Rückschlussregeln](../build/precedence-in-inference-rules.md)

## <a name="see-also"></a>Siehe auch

[NMAKE-Referenz](../build/nmake-reference.md)