---
title: Assemblysprachenkommentare
ms.date: 08/30/2018
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
ms.openlocfilehash: fc37658eccd99b61d45aa9a9a7a2675ef90eee89
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167243"
---
# <a name="assembly-language-comments"></a>Assemblysprachenkommentare

**Microsoft-spezifisch**

Anweisungen in einem `__asm` blockieren kann assemblysprachenkommentare verwenden:

```cpp
__asm mov ax, offset buff ; Load address of buff
```

Da C-Makros in einer einzelnen logischen Zeile erweitern, verwenden Sie keine assemblysprachenkommentare in Makros. (Finden Sie unter [Definieren von __asm-Blöcken als C-Makros](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Ein `__asm` blockieren kann auch im C-Stil Kommentare enthalten; weitere Informationen finden Sie unter [mithilfe von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>