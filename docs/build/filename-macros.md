---
title: Dateinamenmakros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc231dfb156460a2a0cc383b6d038a98c6e2015b
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894407"
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
