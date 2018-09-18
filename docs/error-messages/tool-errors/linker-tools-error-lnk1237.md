---
title: Linkertoolfehler Lnk1237 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9ada38fcf3a706f7852f49f60f677fb5dc10d7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065295"
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