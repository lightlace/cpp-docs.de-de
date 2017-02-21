---
title: "Dateinamenmakros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dateinamenmakros in NMAKE"
  - "Makros, NMAKE"
  - "NMAKE (Programm), Dateinamenmakros"
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Dateinamenmakros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dateinamenmakros sind als Dateinamen vordefiniert, die in der Abhängigkeit angegeben sind \(keine vollständigen Dateinamenangaben auf Datenträger\).  Diese Makros müssen beim Aufruf nicht in Klammern eingeschlossen werden. Geben Sie lediglich `$` an, wie in der folgenden Tabelle gezeigt wird.  
  
|Makro|Bedeutung|  
|-----------|---------------|  
|**$@**|Vollständiger Name des aktuellen Ziels \(Pfad, Basisname, Erweiterung\), wie momentan angegeben.|  
|**$$@**|Vollständiger Name des aktuellen Ziels \(Pfad, Basisname, Erweiterung\), wie momentan angegeben.  Nur als abhängige Datei in einer Abhängigkeit gültig.|  
|**$\***|Pfad und Basisname des aktuellen Ziels ohne Dateierweiterung.|  
|**$\*\***|Alle abhängigen Dateien des aktuellen Ziels.|  
|**$?**|Alle abhängigen Dateien mit einem späteren Timestamp als das aktuelle Ziel.|  
|**$\<**|Abhängige Dateien mit einem späteren Timestamp als das aktuelle Ziel.  Nur in Befehlen in Rückschlussregeln gültig.|  
  
 Um einen Teil eines vordefinierten Dateinamenmakros anzugeben, wird ein Makromodifizierer angefügt und das geänderte Makro in Klammern eingeschlossen.  
  
|Modifizierer|Teil des Dateinamens|  
|------------------|--------------------------|  
|**D**|Laufwerk plus Verzeichnis|  
|**B**|Basisname|  
|**F**|Basisname plus Erweiterung|  
|**R**|Laufwerk plus Verzeichnis plus Basisname|  
  
## Siehe auch  
 [Besondere NMAKE\-Makros](../build/special-nmake-macros.md)