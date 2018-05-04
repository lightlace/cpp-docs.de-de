---
title: FpCsr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9defb41a026b32acb4375185f14c903788b91a23
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fpcsr"></a>FpCsr
Dem registrierungszustand enthält auch die X87 FPU-Steuerwort. Die Aufrufkonvention bestimmt diese registrieren, um die nicht veränderlich zu sein.  
  
 Die X87 die FPU Steuerelement Word Register auf die folgenden Standardwerte, zu Beginn der festgelegt programmausführung an:  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved - 0  
FPCSR[8:9]: Precision Control - 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control - 0 (not used)  
```  
  
 Eine aufgerufene Funktion, die keines der Felder innerhalb FPCSR ändert, muss diese vor der Rückgabe an den Aufrufer wiederherstellen. Darüber hinaus muss ein Aufrufer, der keines dieser Felder geändert wurde wiederhergestellt haben sie auf ihre Standardwerte eine aufgerufene Funktion aufrufen, es sei denn, durch die Vereinbarung der aufgerufene die geänderten Werte erwartet.  
  
 Es gibt zwei Ausnahmen von den Regeln bezüglich der nicht-Flüchtigkeit der Steuerelement-Flags:  
  
1.  In Funktionen, deren dokumentierte Zweck die angegebene Funktion nicht flüchtiger FpCsr kennzeichnet.  
  
2.  Wenn nachweislich richtig, ein Programm, die ein Programm, in dem diese Regeln nicht ist, z. B. durch Analyse des gesamten Programms verletzt werden, identisch verhält sich/bedeutet führt ein Verstoß gegen diese Regeln.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)