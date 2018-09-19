---
title: / DISASM | Microsoft-Dokumentation
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
ms.openlocfilehash: 6a5a4d930c47d2a3c2808cbd0a343c5c68de4ac9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707186"
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
