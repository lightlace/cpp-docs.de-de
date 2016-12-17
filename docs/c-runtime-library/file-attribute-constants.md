---
title: "Dateiattributskonstanten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "A_HIDDEN"
  - "_A_NORMAL"
  - "_A_SUBDIR"
  - "_A_RDONLY"
  - "A_NORMAL"
  - "A_SUBDIR"
  - "_A_SYSTEM"
  - "c.constants.file"
  - "_A_HIDDEN"
  - "A_RDONLY"
  - "_A_ARCH"
  - "A_ARCH"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_A_ARCH-Konstante"
  - "_A_HIDDEN-Konstante"
  - "_A_NORMAL-Konstante"
  - "_A_RDONLY-Konstante"
  - "_A_SUBDIR-Konstante"
  - "_A_SYSTEM-Konstante"
  - "Konstanten [C++], Dateiattribute"
  - "Dateiattributskonstante [C++]"
  - "Dateien [C++], Dateiattributskonstanten"
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Dateiattributskonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <io.h>  
```  
  
## Hinweise  
 Diese Konstanten geben den aktuellen Attributen der Datei bzw. des Verzeichnisses angezeigt, die von der Funktion angegeben werden.  
  
 Die Attribute werden mit folgenden Manifestkonstanten dargestellt:  
  
 `_A_ARCH`  
 Archiv.  Legen Sie fest, wenn die Datei geändert wird und die Backup\-Anweisung gelöscht.  Wert: 0x20  
  
 `_A_HIDDEN`  
 Versteckte Datei.  Nicht normalerweise der mit dem DIR\-Befehl, es sei denn, \/AH\- die Option verwendet wird.  Geben Sie Informationen über normale Dateien sowie Dateien mit diesem Attribut.  Wert: 0x02  
  
 `_A_NORMAL`  
 Normal.  Datei kann ohne zur Einschränkung gelesen oder geschrieben werden.  Wert: 0x00  
  
 `_A_RDONLY`  
 Schreibgeschützt.  Datei kann nicht zum Schreiben geöffnet werden, und eine Datei mit demselben Namen kann nicht erstellt werden.  Wert: 0x01  
  
 `_A_SUBDIR`  
 Unterverzeichnis.  Wert: 0x10  
  
 `_A_SYSTEM`  
 Systemdatei.  Nicht normalerweise der mit dem DIR\-Befehl, es sei denn, \/AS\- die Option verwendet wird.  Wert: 0x04  
  
 Mehrere Konstanten können mit dem Operator OR kombiniert werden \(&#124;\).  
  
## Siehe auch  
 [Dateinamen\-Suchfunktionen](../c-runtime-library/filename-search-functions.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)