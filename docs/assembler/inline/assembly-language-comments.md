---
title: Assemblysprachenkommentare | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02f4c493bac5c2a066dc0b24e2a566d49345288d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683325"
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