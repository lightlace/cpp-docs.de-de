---
title: Unformatierte Pseudooperationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b05a4f9d109809161df7cde643439c281121f62
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703260"
---
# <a name="raw-pseudo-operations"></a>Unformatierte Pseudooperationen

Dieses Thema enthält die Pseudo-Vorgänge.

## <a name="remarks"></a>Hinweise

|Pseudo-Vorgang|Beschreibung|
|----------------------|-----------------|
|PROC FRAME [: Ehandler]|Bewirkt, dass MASM auf eine Funktion generieren Eintrag im .pdata-Datensatz der Tabelle und Entladeinformationen in .xdata für eine Funktion der strukturierten Ausnahmebehandlung entladen Verhalten.  Wenn Ehandler vorhanden ist, wird diese Prozedur im .xdata als die sprachspezifischer Handler eingegeben.<br /><br /> Wenn der FRAME-Attribut verwendet wird, muss ihm durch ein. ENDPROLOG-Direktive.  Wenn die Funktion eine blattfunktion ist (gemäß [Funktionstypen](../build/function-types.md)) das FRAME-Attribut ist nicht erforderlich, die übrigen Pseudooperationen.|
|. PUSHREG reg|Generiert einen UWOP_PUSH_NONVOL Entladung-Code-Eintrag für die mit dem aktuellen offset im Prolog angegebenen Registernummer an.<br /><br /> Dies sollte nur mit permanenten Ganzzahlregister verwendet werden.  Für Push-Vorgänge von volatile Register, verwendet ein. ALLOCSTACK 8, stattdessen|
|. SETFRAME Reg, offset|Füllt das Registrieren Feld und den Offset in den Entladeinformationen unter Verwendung des angegebenen Register und Offset. Der Offset muss ein Vielfaches von 16 sein und kleiner als oder gleich 240. Diese Direktive generiert außerdem einen UWOP_SET_FPREG Entladung Code-Eintrag für die angegebene Register, die mit den aktuellen Prologoffset.|
|. ALLOCSTACK Größe|Generiert eine UWOP_ALLOC_SMALL oder einen UWOP_ALLOC_LARGE mit der angegebenen Größe für den aktuellen Offset im Prolog an.<br /><br /> Der Größenoperand muss es sich um ein Vielfaches von 8 sein.|
|. SAVEREG Reg, offset|Erzeugt entweder eine UWOP_SAVE_NONVOL oder einen UWOP_SAVE_NONVOL_FAR Entladung Code-Eintrag für das angegebene Register und den Offset den aktuelle Prologoffset verwenden. Die effizienteste Codierung wählen MASM.<br /><br /> Offset muss positiv und ein Vielfaches von 8 sein.  Offset ist relativ zu der Basis der Prozedur bei der Frame, in der Regel in der RSP oder, wenn der Frame-Pointer, die-Frame-Pointer verwenden.|
|. SAVEXMM128 Reg, offset|Erzeugt entweder eine UWOP_SAVE_XMM128 oder einen UWOP_SAVE_XMM128_FAR Entladung Code-Eintrag für den angegebenen XMM-Register und der aktuelle Prologoffset mit Offset. Die effizienteste Codierung wählen MASM.<br /><br /> Offset muss positiv und ein Vielfaches von 16 sein.  Offset ist relativ zu der Basis der Prozedur bei der Frame, in der Regel in der RSP oder, wenn der Frame-Pointer, die-Frame-Pointer verwenden.|
|. PUSHFRAME [Code]|Generiert einen UWOP_PUSH_MACHFRAME Entladung Codeeintrag an. Wenn der optionale Code angegeben wird, erhält der Entladung Codeeintrag einen Modifizierer von 1. Andernfalls ist der Modifizierer 0.|
|.ENDPROLOG|Signalisiert das Ende der Prologdeklarationen.  Muss in den ersten 255 Bytes der Funktion erfolgen.|

Hier ist eine Beispiel-Funktionsprologs mit richtiger Verwendung der meisten Opcodes:

```
sample PROC FRAME
   db      048h; emit a REX prefix, to enable hot-patching
push rbp
.pushreg rbp
sub rsp, 040h
.allocstack 040h
lea rbp, [rsp+020h]
.setframe rbp, 020h
movdqa [rbp], xmm7
.savexmm128 xmm7, 020h;the offset is from the base of the frame
;not the scaled offset of the frame
mov [rbp+018h], rsi
.savereg rsi, 038h
mov [rsp+010h], rdi
.savereg rdi, 010h; you can still use RSP as the base of the frame
; or any other register you choose
.endprolog

; you can modify the stack pointer outside of the prologue (similar to alloca)
; because we have a frame pointer.
; if we didn’t have a frame pointer, this would be illegal
; if we didn’t make this modification,
; there would be no need for a frame pointer

sub rsp, 060h

; we can unwind from the following AV because of the frame pointer

mov rax, 0
mov rax, [rax] ; AV!

; restore the registers that weren’t saved with a push
; this isn’t part of the official epilog, as described in section 2.5

movdqa xmm7, [rbp]
mov rsi, [rbp+018h]
mov rdi, [rbp-010h]

; Here’s the official epilog

lea rsp, [rbp-020h]
pop rbp
ret
sample ENDP
```

## <a name="see-also"></a>Siehe auch

[Entladehilfen für MASM](../build/unwind-helpers-for-masm.md)