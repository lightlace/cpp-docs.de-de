---
title: / DISASM | Microsoft Docs
ms.date: 1/17/2018
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /disasm
dev_langs: C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d448b92c3436f3d2875bd8d9b8e0af6a7149e065
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="disasm"></a>/DISASM

Drucken Sie die Disassembly Codeabschnitte in der DUMPBIN-Ausgabe.

## <a name="syntax"></a>Syntax

> **/DISASM**{**:**\[**BYTES**|**NOBYTES**]}  

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
