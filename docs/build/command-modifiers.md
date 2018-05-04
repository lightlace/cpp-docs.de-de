---
title: Befehl Modifizierer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3739c053797bdccd08310e17bf669413ead0db48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="command-modifiers"></a>Befehlsmodifizierer
Sie können eine oder mehrere Befehlsmodifizierer vor einem Befehl, der optional durch Leerzeichen oder Tabstopps getrennt angeben. Wie bei Befehlen, müssen die Modifizierer Einzug dargestellt werden.  
  
|Modifizierer|Zweck|  
|--------------|-------------|  
|@*Befehl*|Verhindert die Anzeige des Befehls. Anzeigen von Befehlen wird nicht unterdrückt. Standardmäßig werden alle ausgeführten Befehle von NMAKE ausgegeben. Verwenden Sie die Anzeige für das gesamte Makefile unterdrückt/s; Verwenden Sie **. AUTOMATISCHE** die Anzeige für den Teil des Makefiles unterdrückt.|  
|**-**[`number` ]*Befehl*|Deaktiviert die Überprüfung auf Fehler *Befehl*. Standardmäßig wird NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich NULL zurückgibt. IF -`number` wird NMAKE verwendet wird, beendet werden, wenn der Exitcode überschreitet `number`. Leerzeichen oder Tabstopps können nicht angezeigt werden, zwischen den Beginn der Strichelung und *Anzahl.* Mindestens ein Leerzeichen oder Tabstopp muss angezeigt werden, zwischen `number` und *Befehl*. Verwenden Sie/i, um Fehler beim Überprüfen der für das gesamte Makefile zu deaktivieren; Verwenden Sie **. IGNORIEREN** fehlerüberprüfung für einen Teil der Makefile deaktivieren.|  
|**!** *command*|Führt *Befehl* für jede abhängige Datei Wenn *Befehl* verwendet **$ \* \*** (alle abhängigen Dateien der Abhängigkeit) oder **$?** (alle abhängigen Dateien in die Abhängigkeit mit einem höheren Zeitstempel als Ziel).|  
  
## <a name="see-also"></a>Siehe auch  
 [Befehle in einem Makefile](../build/commands-in-a-makefile.md)