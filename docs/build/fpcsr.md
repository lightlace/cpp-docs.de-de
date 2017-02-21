---
title: "FpCsr | Microsoft Docs"
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
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# FpCsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Registerstatus enthält auch das x87\-FPU\-Steuerwort.  Die Aufrufkonvention weist dieses Register an, nicht flüchtig zu sein.  
  
 Das x87\-FPU\-Steuerwortregister wird beim Programmstart auf die folgenden Standardwerte festgelegt:  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved – 0  
FPCSR[8:9]: Precision Control – 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control – 0 (not used)  
```  
  
 Eine aufgerufene Funktion, die in FPCSR Felder ändert, muss diese vor der Rückgabe an die aufrufende Funktion wiederherstellen.  Darüber hinaus muss eine aufrufende Funktion, die Änderungen an diesen Feldern vornimmt, vor dem Aufrufen einer anderen Funktion diese Felder auf ihre Standardwerte zurücksetzen, sofern von der aufgerufenen Funktion die geänderten Werte nicht erwartet werden.  
  
 Für diese Regeln gibt es zwei Ausnahmen hinsichtlich der Nichtflüchtigkeit von Steuerflags:  
  
1.  In Funktionen, deren dokumentierter Zweck die Änderung nicht flüchtiger FpCsr\-Flags ist.  
  
2.  Wenn die Verletzung der Regeln nachweisbar \(z. B. durch eine vollständige Programmanalyse\) zu einem Programm führt, das sich ebenso verhält\/die gleiche Bedeutung hat wie ein Programm, bei dem diese Regeln nicht verletzt werden.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)