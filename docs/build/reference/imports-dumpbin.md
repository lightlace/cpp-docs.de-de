---
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: c8b0f88b38eb657fe4d3916ef0df13972e985cbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291839"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Diese Option zeigt die Liste der DLLs (sowohl die statisch verknüpfte und [verzögert geladene](linker-support-for-delay-loaded-dlls.md)), die in eine ausführbare Datei oder DLL und alle einzelnen Importe aus jeder dieser DLLs importiert werden.

Der optionale `file` Spezifikation können Sie angeben, dass die Importe nur diese DLL angezeigt werden. Zum Beispiel:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Hinweise

Die Ausgabe angezeigt, die durch diese Option ist vergleichbar mit der [/EXPORTS](dash-exports.md) Ausgabe.

Nur die [/Headers](headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in Dateien mit der ["/ GL"](gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)
