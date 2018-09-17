---
title: Abgeleitet von abhängige Dateien und Regeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13ae7784ff40b39642ce26fd062a1aab80f2d4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707550"
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