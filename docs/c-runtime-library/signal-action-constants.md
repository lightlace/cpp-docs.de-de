---
title: "Signalaktionskonstanten"
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
  - "SIG_IGN"
  - "SIG_DFL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SIG_DFL-Konstante"
  - "SIG_IGN-Konstante"
  - "Signalaktionskonstante"
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Signalaktionskonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Aktion, wenn das Unterbrechungssignal empfangen wird, hängt vom Wert von `func` ab.  
  
## Syntax  
  
```  
#include <signal.h>  
```  
  
## Hinweise  
 Das `func`\-Argument muss entweder einer Funktionsadresse oder eine der Manifestkonstanten sein, unten aufgeführten werden und in SIGNAL.H. definiert sind.  
  
 `SIG_DFL`  
 Verwendungssystemstandardantwort.  Wenn die aufrufende Programm\-Verwendung E\/A streamt, werden die Puffer, die durch die Laufzeitbibliothek erstellt werden, nicht entfernt.  
  
 `SIG_IGN`  
 Ignoriert Unterbrechungssignal.  Dieser Wert sollte nie für `SIGFPE` angegeben werden, da der Gleitkommazustand des Prozesses nicht definiert verursacht werden.  
  
 `SIG_SGE`  
 Gibt einen Fehler auftrat im Signal an.  
  
 `SIG_ACK`  
 Gibt eine Bestätigung empfangen wurde an.  
  
 `SIG_ERR`  
 Ein Rückgabetyp von einem Signal, das einen Fehler angibt, ist aufgetreten.  
  
## Siehe auch  
 [signal](../c-runtime-library/reference/signal.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)