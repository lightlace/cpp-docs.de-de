---
title: "PogoSafeMode | Microsoft Docs"
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
  - "PogoSafeMode"
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# PogoSafeMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Geben Sie an, ob der schnelle oder abgesicherte Modus zur Anwendungsprofilerstellung verwendet werden soll.  
  
## Syntax  
  
```  
PogoSafeMode  
```  
  
## Hinweise  
 Profilgesteuerte Optimierung \(PGO\) besitzt zwei mögliche Modi während der Profilerstellungsphase: den schnellen und den abgesicherten Modus.  Wenn die Profilerstellung im schnellen Modus stattfindet, werden Datenindikatoren mithilfe der **INC**\-Anweisung vergrößert.  Die **INC**\-Anweisung ist schneller, jedoch nicht threadsicher.  Wenn die Profilerstellung im abgesicherten Modus stattfindet, werden Datenindikatoren mithilfe der **LOCK INC**\-Anweisung vergrößert.  Die **LOCK INC**\-Anweisung besitzt die gleiche Funktion wie die **INC**\-Anweisung und ist threadsicher, dabei jedoch langsamer als die **INC**\-Anweisung.  
  
 Standardmäßig wird PGO\-Profilerstellung im schnellen Modus ausgeführt.  `PogoSafeMode` ist nur erforderlich, wenn Sie den abgesicherten Modus verwenden möchten.  
  
 Um PGO\-Profilerstellung im abgesicherten Modus auszuführen, müssen Sie entweder die Umgebungsvariable `PogoSafeMode` oder den Linkerschalter **\-PogoSafeMode** verwenden \(abhängig vom System\).  Wenn Sie die Profilerstellung auf einem x64\-Computer ausführen, müssen Sie den Linkerschalter verwenden.  Wenn Sie die Profilerstellung auf einem x86\-Computer ausführen, müssen Sie die Umgebungsvariable auf einen beliebigen Wert festlegen, bevor Sie den Optimierungsprozess starten.  
  
## Beispiel  
  
```  
set PogoSafeMode=1  
```  
  
## Siehe auch  
 [Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [Profilgesteuerte Optimierungen \(PGO\)](../../build/reference/profile-guided-optimizations.md)