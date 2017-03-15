---
title: "MxCsr | Microsoft Docs"
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
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# MxCsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Registerstatus schließt auch MxCsr ein.  Durch die Aufrufkonvention wird dieses Register in einen flüchtigen und einen nicht flüchtigen Teil eingeteilt.  Der flüchtige Teil \(MXCSR\[0:5\]\) besteht aus den 6 Statusflags, während das übrige Register \(MXCSR\[6:15\]\) nicht flüchtig ist.  
  
 Der nicht flüchtige Teil wird beim Programmstart auf die folgenden Standardwerte festgelegt:  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 Eine aufgerufene Funktion, die in MXCSR nicht flüchtige Felder ändert, muss diese vor der Rückgabe an die aufrufende Funktion wiederherstellen.  Darüber hinaus muss eine aufrufende Funktion, die Änderungen an diesen Feldern vornimmt, vor dem Aufrufen einer anderen Funktion diese Felder auf ihre Standardwerte zurücksetzen, sofern von der aufgerufenen Funktion die geänderten Werte nicht erwartet werden.  
  
 Für diese Regeln gibt es zwei Ausnahmen hinsichtlich der Nichtflüchtigkeit von Steuerflags:  
  
-   In Funktionen, deren dokumentierter Zweck die Änderung nicht flüchtiger MxCsr\-Flags ist  
  
-   Wenn die Verletzung der Regeln nachweisbar \(z. B. durch eine vollständige Programmanalyse\) zu einem Programm führt, das sich ebenso verhält\/die gleiche Bedeutung hat wie ein Programm, bei dem diese Regeln nicht verletzt werden.  
  
 Über den Zustand des flüchtigen Teils von MXCSR können funktionsübergreifend keine Annahmen gemacht werden, solange dieser nicht ausdrücklich in der Dokumentation der Funktion beschrieben wird.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)