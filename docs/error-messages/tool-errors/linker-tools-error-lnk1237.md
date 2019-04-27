---
title: Linkertoolfehler LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: ae1a397cdcc10cd89fd046a94e78c15dd46dceed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242530"
---
# <a name="linker-tools-error-lnk1237"></a>Linkertoolfehler LNK1237

während der codegenerierung eingeführt Compiler Verweis auf das Symbol 'Symbol' definiert, die im Modul "Module" mit "/ GL" kompiliert

Während der codegenerierung, sollte der Compiler keine Symbole, die später auf Definitionen, die kompiliert aufgelöst werden einführen **"/ GL"**. `symbol` ist ein Symbol, das eingeführt und in einer Definition mit kompiliert aufgelöst wurde **"/ GL"**.

Weitere Informationen finden Sie unter [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).

Um LNK1237 zu beheben, kompilieren Sie nicht die Symbolbreite **"/ GL"** oder [/Include (Symbolverweise erzwingen)](../../build/reference/include-force-symbol-references.md) um einen Verweis auf das Symbol zu erzwingen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK1237 generiert. Um diesen Fehler zu beheben, nicht initialisieren Sie das Array in LNK1237_a.cpp, und fügen **/ include: __chkstk** auf den Linkbefehl.

```
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```