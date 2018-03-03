---
title: Befehl Modifizierer | Microsoft Docs
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
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 610725bf52522cd5041d2f6dcadb422bf942458a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-modifiers"></a>Befehlsmodifizierer
Sie können eine oder mehrere Befehlsmodifizierer vor einem Befehl, der optional durch Leerzeichen oder Tabstopps getrennt angeben. Wie bei Befehlen, müssen die Modifizierer Einzug dargestellt werden.  
  
|Modifizierer|Zweck|  
|--------------|-------------|  
|@*Befehl*|Verhindert die Anzeige des Befehls. Anzeigen von Befehlen wird nicht unterdrückt. Standardmäßig werden alle ausgeführten Befehle von NMAKE ausgegeben. Verwenden Sie die Anzeige für das gesamte Makefile unterdrückt/s; Verwenden Sie **. AUTOMATISCHE** die Anzeige für den Teil des Makefiles unterdrückt.|  
|**-**[`number` ]*Befehl*|Deaktiviert die Überprüfung auf Fehler *Befehl*. Standardmäßig wird NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich NULL zurückgibt. IF -`number` wird NMAKE verwendet wird, beendet werden, wenn der Exitcode überschreitet `number`. Leerzeichen oder Tabstopps können nicht angezeigt werden, zwischen den Beginn der Strichelung und *Anzahl.* Mindestens ein Leerzeichen oder Tabstopp muss angezeigt werden, zwischen `number` und *Befehl*. Verwenden Sie/i, um Fehler beim Überprüfen der für das gesamte Makefile zu deaktivieren; Verwenden Sie **. IGNORIEREN** fehlerüberprüfung für einen Teil der Makefile deaktivieren.|  
|**!** *command*|Führt *Befehl* für jede abhängige Datei Wenn *Befehl* verwendet  **$ \* \***  (alle abhängigen Dateien der Abhängigkeit) oder **$?** (alle abhängigen Dateien in die Abhängigkeit mit einem höheren Zeitstempel als Ziel).|  
  
## <a name="see-also"></a>Siehe auch  
 [Befehle in einem Makefile](../build/commands-in-a-makefile.md)