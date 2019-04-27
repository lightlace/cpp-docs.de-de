---
title: .SETFRAME
ms.date: 08/30/2018
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: c2c35cdb2889350b27e9fb11c397b684506972c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178175"
---
# <a name="setframe"></a>.SETFRAME

Füllt das Feld und den Offset der Entladung-Informationen, die unter Verwendung der angegebene Register zu registrieren (`reg`) und Offset (`offset`). Der Offset muss ein Vielfaches von 16 sein und kleiner als oder gleich 240. Diese Direktive generiert außerdem eine `UWOP_SET_FPREG` Entladen von Codeeintrag für den angegebenen registriert, mit der aktuelle Prologoffset.

## <a name="syntax"></a>Syntax

> . SETFRAME Reg, offset

## <a name="remarks"></a>Hinweise

. SETFRAME ermöglicht ml64.exe angeben, wie eine Funktion des Frames entladen ist nur zulässig, in der Prolog, die von erweitert die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren Sie Code nicht; Generieren sie nur `.xdata` und `.pdata`. . Indem Sie die Anweisungen, die die Aktionen, entladen werden implementieren, sollte SETFRAME vorangestellt werden. Es hat sich bewährt, sowohl den Code, den sie auf die Entladung in einem Makro gedacht sind, um sicherzustellen, dass Vereinbarung als auch die Entladung Anweisungen zu umschließen.

Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="sample"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt, wie Sie die Frame-Pointer verwenden:

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

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>