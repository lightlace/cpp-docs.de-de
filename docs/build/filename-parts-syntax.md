---
title: "Syntax für Dateinamenteile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a481f8c461cb4fddd4acb090edb2f2b5fd18636d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="filename-parts-syntax"></a>Syntax für Dateinamenteile
Syntax für Teile von Dateinamen in Befehlen repräsentiert die Komponenten des ersten abhängigen Dateinamens (die eine implizite abhängige sein kann). Dateinamenkomponenten sind Laufwerk, Pfad, Basisnamen und Erweiterung entsprechend den Angaben, der Datei nicht, wie sie auf dem Datenträger vorhanden ist. Verwendung **%s** zur Darstellung der vollständige Dateiname. Verwendung **% &#124;** [*Teile*]**F** (ein senkrechter Strich hinter das Prozentzeichen) Bestandteile der Dateiname dargestellt, in denen *Teile* 0 (null) oder mehrere der folgenden Buchstaben in beliebiger Reihenfolge.  
  
|Buchstabe|Beschreibung|  
|------------|-----------------|  
|Kein Buchstabe|Vollständigen Namen (wie **%s**)|  
|**d**|Laufwerk|  
|**p**|Pfad|  
|**f**|Basisname|  
|**e**|Dateierweiterung|  
  
 Angenommen, der Dateiname c:\prog.exe ist:  
  
-   %s wird c:\prog.exe sein.  
  
-   % &#124; F wird c:\prog.exe sein.  
  
-   % &#124; dF wird von c  
  
-   % &#124; wird von pF c:\ werden  
  
-   % &#124; wird von fF Komponentenform werden  
  
-   % &#124; wird von eF exe-Datei sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Befehle in einem Makefile](../build/commands-in-a-makefile.md)