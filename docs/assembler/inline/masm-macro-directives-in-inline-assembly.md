---
title: MASM-Makroanweisungen in der Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfd8e3ca5fb6bf65a288c17b1754d567b2b081a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="masm-macro-directives-in-inline-assembly"></a>MASM-Makroanweisungen in der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Der Inlineassembler ist ein Makroassembler. Sie können keine MASM-makrodirektiven (**MAKRO**, `REPT`, **IRC**, `IRP`, und `ENDM`) oder Makro-Operatoren (**<>**, **!** , **&**, `%`, und `.TYPE`). Ein `__asm` Block C#-Präprozessordirektiven, jedoch verwenden kann. Finden Sie unter [mithilfe von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) für Weitere Informationen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)