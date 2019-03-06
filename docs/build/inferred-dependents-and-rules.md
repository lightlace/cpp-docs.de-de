---
title: Hergeleitete abhängige Dateien und Regeln
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: 125d64c47fb8ac9cd86269bedf246a131eda57e7
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414837"
---
# <a name="inferred-dependents-and-rules"></a>Hergeleitete abhängige Dateien und Regeln

NMAKE: eine hergeleitete abhängige für ein Ziel geht davon aus, wenn eine anwendbare Rückschlussregel vorhanden ist. Wenn eine Regel angewendet wird:

- *Toext* der Erweiterung des Ziels übereinstimmt.

- *Fromext* Übereinstimmungen, die die Erweiterung der Datei, die den Namen des Ziels Basis und auf dem, die in der aktuellen oder angegebenen Verzeichnis vorhanden ist.

- *Fromext* befindet sich im [. SUFFIXE](../build/dot-directives.md); keine anderen *Fromext* in eine entsprechende Regel besitzt eine höhere **. SUFFIXE** Priorität.

- Keine explizite abhängige Datei besitzt eine höhere **. SUFFIXE** Priorität.

Hergeleitete abhängige Dateien können unerwartete Nebenwirkungen. Die Beschreibung der Zielblock Befehle enthält, werden diese Befehle die Befehle von NMAKE in der Regel ausgeführt.

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](../build/inference-rules.md)
