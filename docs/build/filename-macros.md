---
title: Dateinamenmakros
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
ms.openlocfilehash: 38fe4408ebfbc2503fcb6be5b53c18d430067aa6
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419681"
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

[Besondere NMAKE-Makros](../build/special-nmake-macros.md)
