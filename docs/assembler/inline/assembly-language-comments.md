---
title: Assemblysprachenkommentare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b93f00aac6151471c1e36b29b2d9f5c3cdbdc1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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