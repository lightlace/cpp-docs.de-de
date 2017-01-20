---
title: "Tools.ini und NMAKE"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMAKE (Programm), Lesen von Dateien"
  - "Tools.ini und NMAKE"
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Tools.ini und NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Datei Tools.ini wird von NMAKE gelesen, bevor Makefiles gelesen werden, es sei denn, \/R wird verwendet.  Zuerst wird Tools.ini im aktuellen Verzeichnis und anschließend in dem Verzeichnis gesucht, das von der INIT\-Umgebungsvariablen angegeben wird.  Der Abschnitt für die NMAKE\-Einstellungen in der Initialisierungsdatei beginnt mit `[NMAKE]` und kann beliebige Makefileinformationen enthalten.  Kommentare sollten in einer separaten Zeile, die mit dem Nummernzeichen \(**\#**\) beginnt, angegeben werden.  
  
## Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)