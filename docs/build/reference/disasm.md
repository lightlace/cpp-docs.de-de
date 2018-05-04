---
title: / DISASM | Microsoft Docs
ms.date: 1/17/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /disasm
dev_langs:
- C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89b0784ff10e7d9521351e01d8907c963c9304fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="disasm"></a>/DISASM

Drucken Sie die Disassembly Codeabschnitte in der DUMPBIN-Ausgabe.

## <a name="syntax"></a>Syntax

> **/ DISASM**{**:**\[**BYTES**|**NOBYTES**]}  

### <a name="arguments"></a>Argumente

**BYTES**  
Enthält die Anweisung Bytes zusammen mit dem interpretierte Opcodes und Argumente in der Ausgabe für die Disassembly. Dies ist die Standardoption.

**NOBYTES**  
Umfasst nicht die Anweisung Bytes in der Ausgabe für die Disassembly.

## <a name="remarks"></a>Hinweise

Die **DISASM** Option zeigt Disassembly Codeabschnitte in der Datei. Debugsymbole werden verwendet, wenn sie in der Datei vorhanden sind.

**/ DISASM** sollte nur für systemeigene, nicht verwalteten Images verwendet werden. Das entsprechende Tool für verwalteten Code ist ["Ildasm"](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung auf Dateien, die von der [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)  
