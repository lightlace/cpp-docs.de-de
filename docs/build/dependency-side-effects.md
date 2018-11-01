---
title: Seiteneffekte bei Abhängigkeiten
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
ms.openlocfilehash: 4ce32a55e89d78d45bc74ce3f7dd45ff2f99af31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530051"
---
# <a name="dependency-side-effects"></a>Seiteneffekte bei Abhängigkeiten

Wenn ein Ziel mit einem Doppelpunkt (:) in zwei Abhängigkeitszeilen an verschiedenen Standorten angegeben wird, und Befehle nach nur eine der Zeilen angezeigt werden, wird von NMAKE, wenn neben oder die kombinierte die Abhängigkeiten interpretiert. Rückschlussregel für die Abhängigkeit wird nicht aufgerufen werden, die keine Befehle, aber stattdessen wird davon ausgegangen, dass die Abhängigkeiten, die eine Beschreibungsblock gehören, und führt die Befehle, die mit den anderen Abhängigkeit angegeben. Legen Sie z. B. diese Regeln:

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

Wie wird ausgewertet werden:

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Dieser Effekt tritt nicht auf, wenn zwei Doppelpunkte (`::`) verwendet wird. Legen Sie z. B. diese Regeln:

```Output
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

Wie wird ausgewertet werden:

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

## <a name="see-also"></a>Siehe auch

[Ziele](../build/targets.md)