---
title: MASM-Makrodirektiven in der Inlineassembly
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 7e1bed782d28a5bf7c934c3f57f50aae70038578
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167256"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>MASM-Makrodirektiven in der Inlineassembly

**Microsoft-spezifisch**

Der Inlineassembler ist kein Makroassembler. Sie können keine MASM-makroanweisungen (**MAKRO**, `REPT`, **IRC**, `IRP`, und `ENDM`) oder Makro-Operatoren (**<>**, **!** , **&**, `%`, und `.TYPE`). Ein `__asm` Block C-präprozessoranweisungen, jedoch verwenden kann. Finden Sie unter [mithilfe von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) für Weitere Informationen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>