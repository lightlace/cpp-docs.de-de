---
title: _emit-pseudoanweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 569e3a078109e66df7dcf5cbf314817ce0786899
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061924"
---
# <a name="emit-pseudoinstruction"></a>_emit Pseudoinstruction

**Microsoft-spezifisch**

Die **_emit** Pseudoinstruction definiert ein Byte an der aktuellen Position in der aktuellen Textsegment. Die **_emit** Pseudoinstruction ähnelt der [DB](../../assembler/masm/db.md) -Direktive der MASM.

Das folgende Fragment platziert die Bytes 0x4A, 0 x 43 und 0x4B in den Code ein:

```cpp
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B
.
.
.
__asm {
    randasm
    }
```

> [!CAUTION]
> Wenn `_emit` Anweisungen generiert, die Register, ändern Sie kompilieren die Anwendung mit aktivierten Optimierungen und der Compiler nicht ermitteln, welche Register betroffen sind. Z. B. wenn `_emit` generiert eine Anweisung, die ändert die **Rax** registrieren, der Compiler ist nicht bekannt, die **Rax** hat sich geändert. Der Compiler kann dann, die falsche Annahme über den Wert, nach der Ausführung der Inlineassemblercode zu registrieren. Daher kann Ihre Anwendung unvorhersehbares Verhalten aufweisen, wenn er ausgeführt wird.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>