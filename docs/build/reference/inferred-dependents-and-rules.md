---
title: Hergeleitete abhängige Dateien und Regeln
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: b9c3055db0cc173999e1737986166eb334dcf96c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825598"
---
# <a name="inferred-dependents-and-rules"></a>Hergeleitete abhängige Dateien und Regeln

NMAKE: eine hergeleitete abhängige für ein Ziel geht davon aus, wenn eine anwendbare Rückschlussregel vorhanden ist. Wenn eine Regel angewendet wird:

- *Toext* der Erweiterung des Ziels übereinstimmt.

- *Fromext* Übereinstimmungen, die die Erweiterung der Datei, die den Namen des Ziels Basis und auf dem, die in der aktuellen oder angegebenen Verzeichnis vorhanden ist.

- *Fromext* befindet sich im [. SUFFIXE](dot-directives.md); keine anderen *Fromext* in eine entsprechende Regel besitzt eine höhere **. SUFFIXE** Priorität.

- Keine explizite abhängige Datei besitzt eine höhere **. SUFFIXE** Priorität.

Hergeleitete abhängige Dateien können unerwartete Nebenwirkungen. Die Beschreibung der Zielblock Befehle enthält, werden diese Befehle die Befehle von NMAKE in der Regel ausgeführt.

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](inference-rules.md)
