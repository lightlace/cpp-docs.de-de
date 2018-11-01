---
title: /DISASM
ms.date: 1/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 77f6f05029ec4480afb2180eab0bb57838d643a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462945"
---
# <a name="disasm"></a>/DISASM

Drucken Sie die Disassemblierung der Codeabschnitte in der Ausgabe von DUMPBIN.

## <a name="syntax"></a>Syntax

> **/ DISASM**{**:**\[**BYTES**|**NOBYTES**]}

### <a name="arguments"></a>Argumente

**BYTES**<br/>
Enthält die Anweisung Bytes zusammen mit den interpretierten Opcodes und die Argumente in der Disassembly-Ausgabe. Dies ist die Standardoption.

**NOBYTES**<br/>
Umfasst nicht die Bytes der Anweisung in der Disassembly-Ausgabe.

## <a name="remarks"></a>Hinweise

Die **DISASM** Option zeigt die Disassemblierung der Codeabschnitte in der Datei. Er verwendet die Debugsymbole, wenn sie in der Datei vorhanden sind.

**/ DISASM** sollte nur für nicht verwaltete, native Images verwendet werden. Das entsprechende Tool für verwalteten Code ist [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung auf Dateien, die von der [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)
