---
title: "Hergeleitete abhängige Dateien und Regeln | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe7c49607f466d8fd1d333883414b24d7837432b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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