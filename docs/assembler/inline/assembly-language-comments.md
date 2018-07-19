---
title: Assemblysprachenkommentare | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 048635a874db604f872b4fa87d72bd06d0455438
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050762"
---
# <a name="assembly-language-comments"></a>Assemblysprachenkommentare
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Anweisungen in einer `__asm` Block assemblysprachenkommentare verwenden kann:  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Da C-Makros in einer einzigen logischen Zeile erweitern, vermeiden Sie die Verwendung von assemblysprachenkommentare in Makros. (Siehe [Definieren von __asm-Blöcken als C-Makros](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) Ein `__asm` Block kann auch C-Stil Kommentare enthalten; weitere Informationen finden Sie unter [mithilfe von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)