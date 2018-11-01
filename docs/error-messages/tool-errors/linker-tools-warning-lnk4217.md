---
title: Linkertoolwarnung LNK4217
ms.date: 11/04/2016
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 12766241832d39f0b47ed85036c0ebeb0447fc75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448047"
---
# <a name="linker-tools-warning-lnk4217"></a>Linkertoolwarnung LNK4217

Lokal definiertes Symbol 'Symbol' in Funktion 'Funktion' importiert

[von "__declspec(dllimport)" "](../../cpp/dllexport-dllimport.md) wurde für ein Symbol angegeben, obwohl das Symbol lokal definiert wurde. Entfernen Sie die `__declspec` Modifizierer, um diese Warnung zu beheben.

`symbol` ist der Symbolname, der innerhalb des Bilds definiert ist. `function` ist die Funktion, die das Symbol importiert wird.

Diese Warnung wird nicht angezeigt, wenn Sie Kompilieren mit der Option ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).

LNK4217 kann auch auftreten, wenn Sie versuchen, zwei Module miteinander zu verknüpfen, wenn stattdessen das zweite Modul mit der Importbibliothek her, der das erste Modul Kompilieren werden soll.

```
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

und anschließend

```
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Es wird versucht, verknüpfen Sie diese beiden Module LNK4217 deutlichen, kompilieren Sie das zweite Beispiel mit der Importbibliothek des ersten zu beheben.