---
title: Syntax für Dateinamenteile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d807087be171a2ad63ed37a8b359c3200c812040
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367484"
---
# <a name="filename-parts-syntax"></a>Syntax für Dateinamenteile
Syntax für Teile von Dateinamen in Befehlen repräsentiert die Komponenten des ersten abhängigen Dateinamens (die eine implizite abhängige sein kann). Dateinamenkomponenten sind Laufwerk, Pfad, Basisnamen und Erweiterung entsprechend den Angaben, der Datei nicht, wie sie auf dem Datenträger vorhanden ist. Verwendung **%s** zur Darstellung der vollständige Dateiname. Verwendung **%&#124;**[*Teile*]**F** (ein senkrechter Strich hinter das Prozentzeichen) Bestandteile der Dateiname dargestellt, in denen *Teile*0 (null) oder mehrere der folgenden Buchstaben, in beliebiger Reihenfolge.  
  
|Buchstabe|Beschreibung|  
|------------|-----------------|  
|Kein Buchstabe|Vollständigen Namen (wie **%s**)|  
|**d**|Laufwerk|  
|**p**|Pfad|  
|**f**|Basisname|  
|**e**|Dateierweiterung|  
  
 Angenommen, der Dateiname c:\prog.exe ist:  
  
-   %s wird c:\prog.exe sein.  
  
-   %&#124;F werden c:\prog.exe  
  
-   %&#124;dF werden c  
  
-   %&#124;pF werden c:\  
  
-   %&#124;fF werden Komponentenform  
  
-   %&#124;eF werden exe-Datei  
  
## <a name="see-also"></a>Siehe auch  
 [Befehle in einem Makefile](../build/commands-in-a-makefile.md)