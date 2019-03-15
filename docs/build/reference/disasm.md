---
title: /DISASM
ms.date: 1/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 10e8187e896b3922438a8cf2dafa0aec4c91f904
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57822534"
---
# <a name="disasm"></a>/DISASM

Drucken Sie die Disassemblierung der Codeabschnitte in der Ausgabe von DUMPBIN.

## <a name="syntax"></a>Syntax

> **/DISASM**{**:**\[**BYTES**|**NOBYTES**]}

### <a name="arguments"></a>Argumente

**BYTES**<br/>
Enthält die Anweisung Bytes zusammen mit den interpretierten Opcodes und die Argumente in der Disassembly-Ausgabe. Dies ist die Standardoption.

**NOBYTES**<br/>
Umfasst nicht die Bytes der Anweisung in der Disassembly-Ausgabe.

## <a name="remarks"></a>Hinweise

Die **DISASM** Option zeigt die Disassemblierung der Codeabschnitte in der Datei. Er verwendet die Debugsymbole, wenn sie in der Datei vorhanden sind.

**/ DISASM** sollte nur für nicht verwaltete, native Images verwendet werden. Das entsprechende Tool für verwalteten Code ist [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Nur die [/Headers](headers.md) DUMPBIN-Option ist verfügbar für die Verwendung auf Dateien, die von der [/GL (Optimierung des ganzen Programms)](gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)
