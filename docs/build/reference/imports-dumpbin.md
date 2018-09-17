---
title: -IMPORTS (DUMPBIN) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5b3b1e3a74fea278bc142d02f793308b6b0e054
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713569"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Diese Option zeigt die Liste der DLLs (sowohl die statisch verknüpfte und [verzögert geladene](../../build/reference/linker-support-for-delay-loaded-dlls.md)), die in eine ausführbare Datei oder DLL und alle einzelnen Importe aus jeder dieser DLLs importiert werden.

Der optionale `file` Spezifikation können Sie angeben, dass die Importe nur diese DLL angezeigt werden. Zum Beispiel:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Hinweise

Die Ausgabe angezeigt, die durch diese Option ist vergleichbar mit der [/EXPORTS](../../build/reference/dash-exports.md) Ausgabe.

Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in Dateien mit der ["/ GL"](../../build/reference/gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)