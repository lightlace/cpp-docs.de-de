---
title: Syntax für Dateinamenteile
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: d5e815dcb8a424d309362e004d1de4c039dc968b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826180"
---
# <a name="filename-parts-syntax"></a>Syntax für Dateinamenteile

Syntax für Teile von Dateinamen in Befehlen repräsentiert die Komponenten des der erste abhängige Dateiname (der eine implizite abhängig sein kann). FileName-Komponenten sind Laufwerk, Pfad, Basisname und angegebene Erweiterung der Datei nicht, wie sie auf dem Datenträger vorhanden ist. Verwendung **%s** kann der vollständige Dateiname repräsentieren. Verwendung **%&#124;**[*Teile*]**F** (ein senkrechter Strich hinter das Prozentzeichen) zum Teilen des Dateinamen darstellen, in denen *Teile*0 (null) oder mehrere der folgenden Buchstaben, in beliebiger Reihenfolge.

|Buchstabe|Beschreibung|
|------------|-----------------|
|Kein Buchstabe|Vollständigen Namen (identisch mit **%s**)|
|**d**|Laufwerk|
|**p**|Pfad|
|**f**|Basisname|
|**e**|Dateierweiterung|

Wenn beispielsweise der Dateiname c:\prog.exe ist:

- %s wird c:\prog.exe sein.

- %&#124;F werden c:\prog.exe

- %&#124;dF werden c

- %&#124;pF werden c:\

- %&#124;fF werden Prog

- %&#124;eF werden exe-Datei

## <a name="see-also"></a>Siehe auch

[Befehle in einem Makefile](commands-in-a-makefile.md)
