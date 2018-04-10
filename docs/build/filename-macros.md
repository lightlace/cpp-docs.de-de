---
title: Dateinamenmakros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2073e4fcb365b3beb10d4040c0f54d9f61a0431
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="filename-macros"></a>Dateinamenmakros
Dateinamenmakros sind als der Abhängigkeit (nicht der vollständige Dateiname Spezifikationen auf dem Datenträger) angegebene Dateinamen vordefiniert. Diese Makros müssen nicht in Klammern, die beim Aufrufen eingeschlossen werden. Geben Sie nur ein $ wie gezeigt.  
  
|Makro|Bedeutung|  
|-----------|-------------|  
|**$@**|Aktuelle Ziel vollständigen Namen (Pfad, Basisname, Erweiterung), wie zurzeit angegeben.|  
|**$$@**|Aktuelle Ziel vollständigen Namen (Pfad, Basisname, Erweiterung), wie zurzeit angegeben. Nur als abhängige Datei in eine Abhängigkeit gültig.|  
|**$\***|Des Ziels für den aktuellen Pfad und Base Namen ohne die Dateierweiterung.|  
|**$\*\***|Alle abhängigen Elemente des aktuellen Ziels.|  
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