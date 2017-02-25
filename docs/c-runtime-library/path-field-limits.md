---
title: "Begrenzungen f&#252;r Pfadfelder | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_MAX_EXT"
  - "_MAX_DIR"
  - "_MAX_PATH"
  - "_MAX_FNAME"
  - "_MAX_DRIVE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_MAX_DIR-Konstante"
  - "_MAX_DRIVE-Konstante"
  - "_MAX_EXT-Konstante"
  - "_MAX_FNAME-Konstante"
  - "_MAX_PATH-Konstante"
  - "MAX_DIR-Konstante"
  - "MAX_DRIVE-Konstante"
  - "MAX_EXT-Konstante"
  - "MAX_FNAME-Konstante"
  - "Pfadfeldkonstante"
  - "Pfade, Maximalgrenze"
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Begrenzungen f&#252;r Pfadfelder
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
#include <stdlib.h>  
```  
  
## Hinweise  
 Diese Konstanten definieren die maximale Länge für den Pfad und für die einzelnen Felder innerhalb des Pfads.  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_MAX_DIR`|Maximale Länge der Verzeichniskomponente|  
|`_MAX_DRIVE`|Maximale Länge der Laufwerkskomponente|  
|`_MAX_EXT`|Maximale Länge der Erweiterungskomponente|  
|`_MAX_FNAME`|Maximale Länge der Dateinamenkomponente|  
|`_MAX_PATH`|Maximale Länge des vollständigen Pfads|  
  
> [!NOTE]
>  Die C\-Laufzeitunterstützungspfadlängen bis 32768 Buchstaben lang, aber sie ist bis zum Betriebssystem, speziell Dateisystem, diese längeren Pfade zu unterstützen.  Die Summe der Felder sollte `_MAX_PATH` für vollständige Abwärtskompatibilität mit Dateisystemen FAT32 nicht überschreiten.  [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../c-runtime-library/includes/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] und Windows Vista\-NTFS\-Dateisystem\-Stützpfade bis 32768 Buchstaben lang, jedoch nur, wenn die Unicode\-APIs verwendet werden.  Bei langen Pfadnamen stellen Sie dem Pfad die Zeichen \\\\?\\  voran, und verwenden Sie die Unicode\-Versionen der C\-Laufzeitfunktionen.  
  
## Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)