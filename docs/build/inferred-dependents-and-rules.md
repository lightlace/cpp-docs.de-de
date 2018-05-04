---
title: Hergeleitete abhängige Dateien und Regeln | Microsoft Docs
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
ms.openlocfilehash: aae09fd756e0eb4eab3031beb5b4cba8c4d35a40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="inferred-dependents-and-rules"></a>Hergeleitete abhängige Dateien und Regeln
NMAKE übernimmt eine hergeleitete abhängige für ein Ziel aus, wenn eine anwendbare Rückschlussregel vorhanden ist. Eine Regel gilt, wenn:  
  
-   *Toext* mit der Erweiterung des Ziels übereinstimmt.  
  
-   *Fromext* Übereinstimmungen, die die Erweiterung der Datei mit der das Ziel-Basisnamen und dem, in der aktuellen oder angegebenen Verzeichnis vorhanden ist.  
  
-   *Fromext* befindet sich im [. SUFFIXE](../build/dot-directives.md); keine anderen *Fromext* in eine entsprechende Regel besitzt eine höhere **. SUFFIXE** Priorität.  
  
-   Keine explizite abhängige Datei besitzt eine höhere **. SUFFIXE** Priorität.  
  
 Hergeleitete abhängige Dateien können dazu führen, dass unerwartete Nebeneffekte. Wenn der Zielblock Beschreibung Befehle enthält, führt NMAKE dieser Befehle anstelle der Befehle in der Regel.  
  
## <a name="see-also"></a>Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)