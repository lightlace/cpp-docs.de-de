---
title: /DISASM
ms.date: 01/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: fb394b2266470e77c50ce5398aea961c37ac34fb
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927722"
---
# <a name="disasm"></a>/DISASM

Druckt die Disassembly von Code Abschnitten in der dumpbin-Ausgabe.

## <a name="syntax"></a>Syntax

> **/DISASM**{ **:** \[**BYTES**|**NOBYTES**]}

### <a name="arguments"></a>Argumente

**BYTES**<br/>
Schließt die Anweisungs Bytes zusammen mit den interpretierten Opcodes und Argumenten in der disassemblyausgabe ein. Dies ist die Standardoption.

**NOBYTES**<br/>
Schließt die Anweisungs Bytes in der disassemblyausgabe nicht ein.

## <a name="remarks"></a>Hinweise

Die Option **/DISASM** zeigt die Disassemblierungscode Abschnitte in der Datei an. Sie verwendet Debugsymbole, wenn Sie in der Datei vorhanden sind.

**/DISASM** sollte nur für Native, nicht verwaltete Images verwendet werden. Das äquivalente Tool für verwalteten Code ist [Ildasm](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Nur die Option [/Headers](headers.md) DUMPBIN ist für die Verwendung in Dateien verfügbar, die von der/GL-Compileroption [(gesamte Programm Optimierung)](gl-whole-program-optimization.md) erstellt werden.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)
