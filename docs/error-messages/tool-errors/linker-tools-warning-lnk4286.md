---
title: Linkertoolwarnung LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 43ed18808ba5ce632dd7dc7095f7bc30e4497ec9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352436"
---
# <a name="linker-tools-warning-lnk4286"></a>Linkertoolwarnung LNK4286

> Symbol "*Symbol*"definiert "*filename_1.obj*"wird importiert, indem"*filename_2.obj*"

[von "__declspec(dllimport)" "](../../cpp/dllexport-dllimport.md) wurde angegeben, für die *Symbol* , obwohl das Symbol, in der Objektdatei definiert ist *filename_1.obj* im gleichen Abbild. Entfernen Sie die `__declspec(dllimport)` Modifizierer, um diese Warnung zu beheben.

## <a name="remarks"></a>Hinweise

Warnung LNK4286 ist eine allgemeine Version der [Linker Tools Warning LNK4217](linker-tools-warning-lnk4217.md). Der Linker generiert Warnung LNK4286 aus, wenn sie sehen, welche Objektdatei auf das Symbol verwiesen, aber nicht die Funktion.

Um LNK4286 zu beheben, entfernen Sie die `__declspec(dllimport)` deklarationsmodifizierer aus die Vorwärtsdeklaration *Symbol* verwiesen wird, im *filename_2.obj*.

Der letzte generierte Code ordnungsgemäß verhält sich, zwar ist der Code zum Aufrufen einer importierten Funktion weniger effizient als direkter Aufruf der Funktion. Diese Warnung nicht angezeigt, wenn Sie bei der Kompilierung der ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) Option.

Weitere Informationen zum Importieren und Exportieren von Datendeklarationen, finden Sie unter [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>Siehe auch

[Linkertoolwarnung Lnk4049](linker-tools-warning-lnk4049.md) \
[Linkertoolwarnung Lnk4217](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)