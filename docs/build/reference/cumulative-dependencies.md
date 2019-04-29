---
title: Kumulative Abhängigkeiten
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: de0a9649be8f0dae58f45d8980d2df610ff2febe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294082"
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

[Ziele](targets.md)
