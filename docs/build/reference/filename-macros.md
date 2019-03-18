---
title: Dateinamenmakros
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
ms.openlocfilehash: 54527c6f06bee396fdc7419647c607f8979c6a38
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825566"
---
# <a name="filename-macros"></a>Dateinamenmakros

Dateinamenmakros sind als der Abhängigkeit (nicht den vollständigen Dateinamen Spezifikationen auf dem Datenträger) angegebene Dateinamen vordefiniert. Diese Makros müssen nicht in Klammern, die beim Aufruf eingeschlossen werden; Geben Sie lediglich an, wie gezeigt.

|Makro|Bedeutung|
|-----------|-------------|
|**$\@**|Aktuelles Ziel vollständigen Namen (Pfad, Basisname, Erweiterung), wie zurzeit angegeben.|
|**$$\@**|Aktuelles Ziel vollständigen Namen (Pfad, Basisname, Erweiterung), wie zurzeit angegeben. Nur als ein abhängiges Element in einer Abhängigkeit gültig.|
|**$&#42;**|Aktuelles Ziel-Pfad und den Basis-Name ohne die Dateierweiterung.|
|**$&#42;&#42;**|Alle abhängigen Elemente des aktuellen Ziels.|
|**$?**|Alle abhängigen Elemente mit dem späteren Zeitstempel, als das aktuelle Ziel.|
|**$<**|Abhängige Datei mit dem späteren Zeitstempel, als das aktuelle Ziel. Nur in Befehlen in Rückschlussregeln gültig.|

Um Teil eines vordefinierten Dateinamenmakros anzugeben, fügen Sie einen Makromodifizierer, und schließen Sie das geänderte-Makro in Klammern ein.

|Modifizierer|Teil des Dateinamens|
|--------------|-----------------------------|
|**D**|Laufwerk und Verzeichnis|
|**B**|Basisname|
|**F**|Basisnamen und Erweiterung|
|**R**|Laufwerk und Verzeichnis mit Basisname|

## <a name="see-also"></a>Siehe auch

[Besondere NMAKE-Makros](special-nmake-macros.md)
