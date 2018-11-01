---
title: Kumulative Abhängigkeiten
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: c31740b830993c91568aea6d167fd3113b04fc57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460280"
---
# <a name="cumulative-dependencies"></a>Kumulative Abhängigkeiten

Abhängigkeiten sind in einem Beschreibungsblock kumulativ, wenn ein Ziel wiederholt wird.

Legen Sie diese z. B. Regeln,

```Output
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

Wie wird ausgewertet werden:

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Mehrere Ziele in mehrere Abhängigkeitszeilen in einem einzelnen Beschreibungsblock werden ausgewertet, als ob jede in einem separaten Beschreibungsblock angegeben wurden, verwenden Sie jedoch Ziele, die nicht in der letzten Abhängigkeitszeile nicht Befehlsblock. NMAKE: versucht, eine Rückschlussregel für diese Ziele zu verwenden.

Legen Sie diese z. B. Regeln,

```Output
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

Wie wird ausgewertet werden:

```Output

leap.exe : jump.obj
# invokes an inference rule
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
climb.exe : up.obj
   echo Building bounce.exe...
```

## <a name="see-also"></a>Siehe auch

[Ziele](../build/targets.md)