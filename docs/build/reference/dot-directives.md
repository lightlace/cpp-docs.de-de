---
title: Punktdirektiven
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
ms.openlocfilehash: 2c21e8a18c76331f86a4e8966b4f67c9c9bc9b7d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342821"
---
# <a name="dot-directives"></a>Punktdirektiven

Geben Sie die Punkt-Direktiven außerhalb eines Blocks Beschreibung am Anfang einer Zeile. Punktanweisungen beginnen mit einem Punkt (. ), gefolgt von einem Doppelpunkt (:). Registerkarten und Leerzeichen sind zulässig. Punkt-Direktivennamen sind Groß-/Kleinschreibung beachtet und Großbuchstaben.

|Direktive|Zweck|
|---------------|-------------|
|**. IGNORIEREN:**|Ignoriert die Exitcodes ungleich NULL zurückgegeben, die von Befehlen, von dem Ort, die sie am Ende das Makefile angegeben ist. Standardmäßig wird Sie NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich NULL zurückgibt. Verwenden Sie zum Wiederherstellen der fehlerüberprüfung **! CMDSWITCHES**. Wenn den Exitcode für einen einzelnen Befehl ignorieren möchten, verwenden Sie den Bindestrich (-)-Modifizierer. Wenn Exitcodes für eine gesamte Datei ignorieren möchten, verwenden Sie / ich.|
|**. PRECIOUS:** *Ziele*|Behält *Ziele* auf dem Datenträger, wenn die Befehle für das Aktualisieren angehalten werden, hat keine Auswirkungen, wenn ein Befehl einen Interrupt behandelt, durch Löschen der Datei. Trennen Sie die Namen der Ziele, durch eine oder mehrere Leerzeichen oder Tabstopps. Standardmäßig löscht NMAKE ein Ziel aus, wenn ein Build, indem Sie STRG + C oder STRG + UNTBR unterbrochen wird. Jede Verwendung von **. WERTVOLLE** gilt für das gesamte Makefile; mehrere Spezifikationen sind kumulativ.|
|**. AUTOMATISCHE:**|Unterdrückt die Anzeige der ausgeführten Befehle, von dem Ort, die sie am Ende das Makefile angegeben ist. Standardmäßig zeigt NMAKE die Befehle, die ihn aufruft. Verwenden Sie zum Wiederherstellen ausgeben **! CMDSWITCHES**. Um Echo für einen einzelnen Befehl zu unterdrücken, verwenden Sie die **@** Modifizierer. Um für eine gesamte Datei ausgeben zu unterdrücken, verwenden Sie/S.|
|**. SUFFIXE:** `list`|Listet die Erweiterungen für den Abgleich von Rückschlussregel; um die folgenden Erweiterungen enthalten vordefinierte: .exe obj .asm .c cpp .cxx BAS .cbl .for .pas Res RC .f .f90|

So ändern Sie die **. SUFFIXE** -Liste zu ändern oder um eine neue Liste angeben möchten, löschen Sie die Liste, und geben Sie eine neue Einstellung. Um die Liste zu löschen, geben Sie keine Erweiterungen nach dem Doppelpunkt ein:

```
.SUFFIXES :
```

Um zusätzliche Suffixe an das Ende der Liste hinzuzufügen, geben

```
.SUFFIXES : suffixlist
```

wo *Suffixlist* ist eine Liste der Suffixe, die durch eine oder mehrere Leerzeichen oder Tabstopps getrennt. Um die aktuelle Einstellung der finden Sie unter **. SUFFIXE**, anzuzeigen NMAKE mit

## <a name="see-also"></a>Siehe auch

[NMAKE-Referenz](nmake-reference.md)
