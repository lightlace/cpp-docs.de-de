---
title: Kumulative Abhängigkeiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a66b153a52da06cca14845b9a58fcef0f42676d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725711"
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