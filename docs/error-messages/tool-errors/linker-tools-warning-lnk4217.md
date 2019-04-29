---
title: Linkertoolwarnung LNK4217
ms.date: 04/15/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: f1ea3cd0a8770571ae5c55d29a901c134311550f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410225"
---
# <a name="linker-tools-warning-lnk4217"></a>Linkertoolwarnung LNK4217

> Symbol "*Symbol*"definiert "*filename_1.obj*"wird importiert, indem"*filename_2.obj*"in Funktion'*Funktion*"

[von "__declspec(dllimport)" "](../../cpp/dllexport-dllimport.md) wurde für ein Symbol angegeben, obwohl das Symbol in einer Objektdatei im gleichen Abbild definiert ist. Entfernen Sie die `__declspec(dllimport)` Modifizierer, um diese Warnung zu beheben.

## <a name="remarks"></a>Hinweise

*Symbol* ist von der Symbolnamen, die innerhalb des Bilds definiert ist. *Funktion* ist die Funktion, die das Symbol importiert wird.

Diese Warnung nicht angezeigt, wenn Sie bei der Kompilierung der ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) Option.

LNK4217 kann auch auftreten, wenn Sie versuchen, zwei Module miteinander zu verknüpfen, wenn stattdessen das zweite Modul mit der Importbibliothek her, der das erste Modul Kompilieren werden soll.

```cpp
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

und anschließend

```cpp
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Es wird versucht, diese beiden Module link führt zu LNK4217. Kompilieren Sie das zweite Beispiel mit der Importbibliothek her, der dem ersten Beispiel, auflösen.

## <a name="see-also"></a>Siehe auch

[Linkertoolwarnung Lnk4049](linker-tools-warning-lnk4049.md) \
[Linkertoolwarnung LNK4286 Warnung](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)