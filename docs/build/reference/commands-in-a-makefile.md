---
title: Befehle in einem Makefile
ms.date: 11/04/2016
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
ms.openlocfilehash: fcb8737070931cf95d7bfb3971a84e22c7ad70a4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825330"
---
# <a name="commands-in-a-makefile"></a>Befehle in einem Makefile

Eine Beschreibung Block oder Typrückschluss-Regel gibt an, ein Block von Befehlen ausführen, wenn die Abhängigkeit nicht aktuell ist. NMAKE: jeder Befehl vor der Ausführung angezeigt, es sei denn, "/ s", **. AUTOMATISCHE**, **! CMDSWITCHES**, oder \@ verwendet wird. NMAKE: sucht nach einer übereinstimmenden Rückschlussregel, wenn ein Beschreibungsblock von einem Befehlsblock nicht befolgt wird.

Ein Befehlsblock enthält einen oder mehrere Befehle, die auf einer eigenen Zeile. Es sind keine Leerzeilen kann zwischen der Abhängigkeit "oder" Regel "und" Befehlsblock angezeigt werden. Allerdings kann eine Zeile, enthält nur Leerzeichen oder Tabstopps angezeigt; Diese Zeile wird als null-Befehl interpretiert, und kein Fehler auftritt. Leere Zeilen dürfen zwischen Befehlszeilen.

Eine Befehlszeile beginnt mit einem oder mehreren Leerzeichen oder Tabstopps. Ein umgekehrter Schrägstrich (\) gefolgt von einem neue Zeilenumbruchzeichen wird als ein Leerzeichen im Befehl interpretiert. Verwenden Sie einen umgekehrten Schrägstrich am Ende einer Zeile, um einen Befehl auf die nächste Zeile fortzusetzen. NMAKE interpretiert den umgekehrten Schrägstrich buchstäblich alle anderen Zeichen, einschließlich von einem Leerzeichen oder Tabstopp, den umgekehrten Schrägstrich folgt.

Ein Befehl vorangestellt wird, wird ein Semikolon (;) auf eine abhängigkeitsregel oder Rückschlussregel angezeigt werden können, und zwar unabhängig davon, ob ein Befehlsblock folgt:

```
project.obj : project.c project.h ; cl /c project.c
```

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Befehlsmodifizierer](command-modifiers.md)

[Syntax für Dateinamenteile](filename-parts-syntax.md)

[Inlinedateien in einem makefile](inline-files-in-a-makefile.md)

## <a name="see-also"></a>Siehe auch

[NMAKE-Referenz](nmake-reference.md)
