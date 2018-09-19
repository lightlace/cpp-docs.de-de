---
title: Seiteneffekte bei Abhängigkeiten | Microsoft-Dokumentation
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
ms.openlocfilehash: 9a70df679434b187bc2eee4eb4aad5881db0da1c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716519"
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