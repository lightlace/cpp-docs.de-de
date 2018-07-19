---
title: Dateinamenmakros | Microsoft Docs
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
ms.openlocfilehash: e28ba5923d8b62973860c0ba503d13682b3c5e79
ms.sourcegitcommit: 3bb7c1c0ceeb8012418e2fff9ae5a7db0fff3877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458861"
---
# <a name="filename-macros"></a>Dateinamenmakros
Dateinamenmakros sind als der Abhängigkeit (nicht der vollständige Dateiname Spezifikationen auf dem Datenträger) angegebene Dateinamen vordefiniert. Diese Makros müssen nicht in Klammern, die beim Aufrufen eingeschlossen werden. Geben Sie nur ein $ wie gezeigt.  
  
|Makro|Bedeutung|  
|-----------|-------------|  
|**$@**|Aktuelle Ziel vollständigen Namen (Pfad, Basisname, Erweiterung), wie zurzeit angegeben.|  
|**$$@**|Aktuelle Ziel vollständigen Namen (Pfad, Basisname, Erweiterung), wie zurzeit angegeben. Nur als abhängige Datei in eine Abhängigkeit gültig.|  
|**$&#42;**|Des Ziels für den aktuellen Pfad und Base Namen ohne die Dateierweiterung.|  
|**$&#42;&#42;**|Alle abhängigen Elemente des aktuellen Ziels.|  
|**$?**|Alle abhängigen Elemente mit einem höheren Zeitstempel als das aktuelle Ziel.|  
|**$<**|Abhängige Datei mit einem höheren Zeitstempel als das aktuelle Ziel. Nur in Befehlen in Rückschlussregeln gültig.|  
  
 Um Teil eines vordefinierten Dateinamenmakros anzugeben, fügen Sie einen Makromodifizierer aus, und schließen Sie das geänderte Makro in Klammern ein.  
  
|Modifizierer|Teil des Dateinamens|  
|--------------|-----------------------------|  
|**D**|Laufwerk plus Verzeichnis|  
|**B**|Basisname|  
|**F**|Basisnamen und Erweiterung|  
|**R**|Laufwerk plus Verzeichnis plus Basisname|  
  
## <a name="see-also"></a>Siehe auch  
 [Besondere NMAKE-Makros](../build/special-nmake-macros.md)
