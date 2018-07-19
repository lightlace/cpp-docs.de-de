---
title: MxCsr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9df2225526c20463bdbd618322d031c3245d9493
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368625"
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