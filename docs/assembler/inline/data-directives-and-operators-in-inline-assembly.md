---
title: Datenanweisungen und Operatoren in der Inlineassembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: 6aff2f4c5ce5e7f5592aa9ec707d002c57f0eac0
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678736"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Datenanweisungen und Operatoren in der Inlineassembly

**Microsoft-spezifisch**

Obwohl eine `__asm` blockieren kann C- oder C++-Datentypen und Objekte verweisen, die Datenobjekte mit MASM-Direktiven oder Operatoren nicht definiert. Insbesondere können keine die Definition-Direktiven **DB**, `DW`, **TT**, `DQ`, `DT`, und `DF`, oder die Operatoren `DUP` oder  **Dies**. MASM-Strukturen und Datensätze sind ebenfalls nicht verfügbar. Der Inlineassembler keine akzeptieren Sie die Anweisungen `STRUC`, `RECORD`, **Breite**, oder **MASKE**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>