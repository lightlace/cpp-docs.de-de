---
title: MxCsr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7794cea8906440c0adca94791d08e3ced6af747e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mxcsr"></a>MxCsr
Dem registrierungszustand hinaus MxCsr. Die Aufrufkonvention unterteilt eine flüchtige Teil und einen nicht flüchtigen Teil dieses Register. Der flüchtige Teil besteht aus den 6 Statusflags MXCSR [0:5], während der Rest des Registers, MXCSR [6:15] flüchtig ist.  
  
 Die flüchtige Teil wird zu Beginn der Ausführung des Programms auf die folgenden Standardwerte festgelegt:  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 Eine aufgerufene Funktion, die die NVRAM Felder im MXCSR ändert, muss diese vor der Rückgabe an den Aufrufer wiederherstellen. Darüber hinaus muss ein Aufrufer, der keines dieser Felder geändert wurde wiederhergestellt haben sie auf ihre Standardwerte eine aufgerufene Funktion aufrufen, es sei denn, durch die Vereinbarung der aufgerufene die geänderten Werte erwartet.  
  
 Es gibt zwei Ausnahmen von den Regeln bezüglich der nicht-Flüchtigkeit der Steuerelement-Flags:  
  
-   In Funktionen, deren dokumentierte Zweck die angegebene Funktion nicht flüchtiger MxCsr-flags.  
  
-   Wenn nachweislich richtig, ein Programm, die ein Programm, in dem diese Regeln nicht ist, z. B. durch Analyse des gesamten Programms verletzt werden, identisch verhält sich/bedeutet führt ein Verstoß gegen diese Regeln.  
  
 Sofern nicht ausdrücklich in der Dokumentation der Funktion beschrieben, können keine Annahmen über den Zustand des flüchtigen Teils des MXCSR Apartmentgrenze eine Funktion vorgenommen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)