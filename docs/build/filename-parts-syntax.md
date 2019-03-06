---
title: Syntax für Dateinamenteile
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: 159558081fd9884f969ddc66833d927b8569a79b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417475"
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

[Befehle in einem Makefile](../build/commands-in-a-makefile.md)
