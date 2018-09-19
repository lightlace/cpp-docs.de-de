---
title: MASM-Makroanweisungen in der Inlineassembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: 35ad22a9a4b79a31665ab6b156f8174d395bb0ee
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "43687972"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>MASM-Makroanweisungen in der Inlineassembly

**Microsoft-spezifisch**

Der Inlineassembler ist kein Makroassembler. Sie können keine MASM-makroanweisungen (**MAKRO**, `REPT`, **IRC**, `IRP`, und `ENDM`) oder Makro-Operatoren (**<>**, **!** , **&**, `%`, und `.TYPE`). Ein `__asm` Block C-präprozessoranweisungen, jedoch verwenden kann. Finden Sie unter [mithilfe von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) für Weitere Informationen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>