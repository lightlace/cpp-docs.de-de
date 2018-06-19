---
title: Datenanweisungen und Operatoren in der Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bd3bc686cc8cee1a02e9df936f80f542bec26bd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051384"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Datenanweisungen und Operatoren in der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Obwohl eine `__asm` Block kann C- oder C++-Datentypen und Objekte verweisen, Datenobjekte mit MASM-Direktiven oder Operatoren nicht definiert. Insbesondere können Sie keine Richtlinien Definition **DB**, `DW`, **DD**, `DQ`, `DT`, und `DF`, oder die Operatoren `DUP` oder  **Dies**. MASM-Strukturen und Datensätze sind auch nicht verfügbar. Der Inlineassembler keine akzeptieren die Direktiven `STRUC`, `RECORD`, **Breite**, oder **MASKE**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)