---
title: "spawn-Konstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_P_NOWAIT"
  - "_P_OVERLAY"
  - "_P_WAIT"
  - "_P_DETACH"
  - "_P_NOWAITO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_P_DETACH-Konstante"
  - "_P_NOWAIT-Konstante"
  - "_P_NOWAITO-Konstante"
  - "_P_OVERLAY-Konstante"
  - "_P_WAIT-Konstante"
  - "P_DETACH-Konstante"
  - "P_NOWAIT-Konstante"
  - "P_NOWAITO-Konstante"
  - "P_OVERLAY-Konstante"
  - "P_WAIT-Konstante"
  - "spawn-Konstanten"
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# spawn-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
#include <process.h>  
```  
  
## Hinweise  
 Das Argument `mode` bestimmt die Aktionen, die von der aufrufende Prozess vor und während eines Fischeiervorgangs ausgeführt werden.  Die folgenden Werte für `mode` sind möglich:  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_P_OVERLAY`|Überlagert aufrufenden Prozesses mit dem neuen Prozess und zerstört aufrufenden Prozesses \(denselben Effekt der `_exec` aufgerufen\).|  
|`_P_WAIT`|Hält aufrufenden Thread, bis die Ausführung des neuen Vorgangs abgeschlossen wurde \(synchrones `_spawn`\).|  
|`_P_NOWAIT`, `_P_NOWAITO`|Fährt fort, um aufrufende Prozess gleichzeitig mit neuen Prozess \(Asynchronous `_spawn`\) auszuführen.|  
|`_P_DETACH`|Fährt fort, um aufrufende Prozess auszuführen; neuer Prozess wird in Hintergrund ohne Zugriff auf die Konsole oder die Tastatur ausgeführt.  Aufrufe von `_cwait` für neuen Prozess schlagen fehl.  Dies ist asynchrone `_spawn`.|  
  
## Siehe auch  
 [\_spawn\- und \_wspawn\-Funktionen](../c-runtime-library/spawn-wspawn-functions.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)