---
title: .SETFRAME
ms.date: 08/30/2018
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: a21dda496d32abcfeb4692d0228afdbcfd4e5ebb
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397932"
---
# <a name="setframe"></a>.SETFRAME

Füllt das Rahmen Register Feld und den Offset in den Entlade Informationen mit dem angegebenen Register (*reg*) und Offset (*Offset*) aus. Der Offset muss ein Vielfaches von 16 und kleiner oder gleich 240 sein. Diese Direktive generiert außerdem einen `UWOP_SET_FPREG` Entladungs Code Eintrag für das angegebene Register unter Verwendung des aktuellen prologoffsets.

## <a name="syntax"></a>Syntax

> **. SetFrame** - *reg*, *Offset*

## <a name="remarks"></a>Hinweise

**. Mit setFrame** können Benutzer von ml64. exe angeben, wie sich eine Frame Funktion entlädt, und nur innerhalb des Prologs zulässig, der sich von der [proc](../../assembler/masm/proc.md) Frame-Deklaration zum erstreckt [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. **. SetFrame** sollte Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgenden Beispiel wird gezeigt, wie ein Frame Zeiger verwendet wird:

### <a name="code"></a>Code

```asm
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE
_text SEGMENT
frmex2 PROC FRAME
   push rbp
.pushreg rbp
   sub rsp, 010h
.allocstack 010h
   mov rbp, rsp
.setframe rbp, 0
.endprolog
   ; modify the stack pointer outside of the prologue (similar to alloca)
   sub rsp, 060h

   ; we can unwind from the following AV because of the frame pointer
   mov rax, 0
   mov rax, [rax] ; AV!

   add rsp, 060h
   add rsp, 010h
   pop rbp
   ret
frmex2 ENDP
_text ENDS
END
```

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
