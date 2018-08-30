---
title: Befehl Modifizierer | Microsoft-Dokumentation
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
ms.openlocfilehash: c9e1d883e0c7a2b214842b096fdf697ffc7d0192
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221740"
---
# <a name="command-modifiers"></a>Befehlsmodifizierer
Sie können eine oder mehrere Befehlsmodifizierer vor einem Befehl, der optional durch Leerzeichen oder Tabstopps getrennt angeben. Wie bei Befehlen müssen Modifizierer eingerückt werden.  
  
|Modifizierer|Zweck|  
|--------------|-------------|  
|@*Befehl*|Verhindert die Anzeige des Befehls. Anzeigen von Befehlen wird nicht unterdrückt. Standardmäßig werden alle ausgeführten Befehle von NMAKE ausgegeben. Verwenden Sie/s Anzeige für das gesamte Makefile unterdrückt werden soll. Verwenden Sie **. AUTOMATISCHE** Anzeige für den Teil des Makefiles unterdrückt werden soll.|  
|**-**\[*Anzahl*] *Befehl*|Fehler beim Überprüfen auf deaktiviert *Befehl*. Standardmäßig wird Sie NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich NULL zurückgibt. IF -*Anzahl* ist NMAKE verwendet wird, beendet werden, wenn der Exitcode überschreitet *Anzahl*. Leerzeichen oder Tabstopps können nicht verwendet werden, zwischen den Bindestrich und *Anzahl.* Mindestens ein Leerzeichen oder Tabstopp muss angezeigt werden, zwischen `number` und *Befehl*. Verwenden Sie/i, um die Fehler beim Überprüfen der für das gesamte Makefile zu deaktivieren; Verwenden Sie **. IGNORIEREN Sie** fehlerüberprüfung für Teil des Makefiles deaktivieren.|  
|**!** *command*|Führt *Befehl* für jede abhängige Datei Wenn *Befehl* verwendet <strong>$ \* \*</strong> (alle abhängigen Dateien in der Abhängigkeit) oder **$?** (alle abhängigen Dateien in der Abhängigkeit mit dem späteren Zeitstempel, als das Ziel).|  
  
## <a name="see-also"></a>Siehe auch  
 [Befehle in einem Makefile](../build/commands-in-a-makefile.md)