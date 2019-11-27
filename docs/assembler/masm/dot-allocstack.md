---
title: .ALLOCSTACK
ms.date: 08/30/2018
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: 6d9d86371503992d1bebe738fb6e6773581b10e3
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398633"
---
# <a name="allocstack"></a>.ALLOCSTACK

Generiert eine **UWOP_ALLOC_SMALL** oder eine **UWOP_ALLOC_LARGE** mit der angegebenen Größe für den aktuellen Offset im Prolog.

## <a name="syntax"></a>Syntax

> **. Größe des zugewiesenen Stapels**

## <a name="remarks"></a>Hinweise

MASM wählt die effizienteste Codierung für eine bestimmte Größe aus.

**. Mit "Zuordnungs Stapel** " können Benutzer von ml64. exe angeben, wie sich eine Frame Funktion entlädt und nur innerhalb des Prologs zulässig ist, der von der [proc](../../assembler/masm/proc.md) Frame-Deklaration zum reicht [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. **. Zuweisungs Stapel** sollten Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

Der *Größen* Operand muss ein Vielfaches von 8 sein.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein Entlade-/Ausnahmehandler angegeben wird:

```asm
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console
text SEGMENT
PUBLIC Example3
PUBLIC Example3_UW
Example3_UW PROC NEAR
   ; exception/unwind handler body

   ret 0

Example3_UW ENDP

Example3 PROC FRAME : Example3_UW

   sub rsp, 16
.allocstack 16

.endprolog

   ; function body
    add rsp, 16
   ret 0

Example3 ENDP
text ENDS
END
```

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
