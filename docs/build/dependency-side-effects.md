---
title: Seiteneffekte bei Abhängigkeiten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7537e077a43318a487163d014b49d52cef66ce19
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="dependency-side-effects"></a>Seiteneffekte bei Abhängigkeiten
Wenn ein Ziel mit einem Doppelpunkt (:) in beiden Abhängigkeitszeilen an verschiedenen Standorten angegeben ist, und Befehle nach nur eine der Zeilen angezeigt werden, interpretiert NMAKE Abhängigkeiten wie bei angrenzende oder kombiniert. Es keine Rückschlussregel für die Abhängigkeit aufgerufen werden, die keine Befehle, aber stattdessen wird davon ausgegangen, dass die Abhängigkeiten einer Beschreibung Block gehören, und führt die Befehle, die mit den anderen Abhängigkeit angegeben. Legen Sie beispielsweise diese Regeln:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 wird folgendermaßen ausgewertet:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Dieser Effekt tritt nicht auf, wenn zwei Doppelpunkte (`::`) verwendet wird. Legen Sie beispielsweise diese Regeln:  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 wird folgendermaßen ausgewertet:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ziele](../build/targets.md)