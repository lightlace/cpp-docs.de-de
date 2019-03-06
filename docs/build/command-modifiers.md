---
title: Befehlsmodifizierer
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
ms.openlocfilehash: 764b381a057b1cecf85b0bc3c4c5711aa1aac4ec
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413068"
---
# <a name="command-modifiers"></a>Befehlsmodifizierer

Sie können eine oder mehrere Befehlsmodifizierer vor einem Befehl, der optional durch Leerzeichen oder Tabstopps getrennt angeben. Wie bei Befehlen müssen Modifizierer eingerückt werden.

|Modifizierer|Zweck|
|--------------|-------------|
|\@*Befehl*|Verhindert die Anzeige des Befehls. Anzeigen von Befehlen wird nicht unterdrückt. Standardmäßig werden alle ausgeführten Befehle von NMAKE ausgegeben. Verwenden Sie/s Anzeige für das gesamte Makefile unterdrückt werden soll. Verwenden Sie **. AUTOMATISCHE** Anzeige für den Teil des Makefiles unterdrückt werden soll.|
|**-**\[*Anzahl*] *Befehl*|Fehler beim Überprüfen auf deaktiviert *Befehl*. Standardmäßig wird Sie NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich NULL zurückgibt. IF -*Anzahl* ist NMAKE verwendet wird, beendet werden, wenn der Exitcode überschreitet *Anzahl*. Leerzeichen oder Tabstopps können nicht verwendet werden, zwischen den Bindestrich und *Anzahl.* Mindestens ein Leerzeichen oder Tabstopp muss angezeigt werden, zwischen `number` und *Befehl*. Verwenden Sie/i, um die Fehler beim Überprüfen der für das gesamte Makefile zu deaktivieren; Verwenden Sie **. IGNORIEREN Sie** fehlerüberprüfung für Teil des Makefiles deaktivieren.|
|**\!** *command*|Führt *Befehl* für jede abhängige Datei Wenn *Befehl* verwendet <strong>$ \* \*</strong> (alle abhängigen Dateien in der Abhängigkeit) oder **$?** (alle abhängigen Dateien in der Abhängigkeit mit dem späteren Zeitstempel, als das Ziel).|

## <a name="see-also"></a>Siehe auch

[Befehle in einem Makefile](../build/commands-in-a-makefile.md)
