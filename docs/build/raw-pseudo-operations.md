---
title: Unformatierte Pseudooperationen | Microsoft Docs
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
ms.openlocfilehash: ff3b9dd065b4bf1f64950f97237dec08b10d23cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369928"
---
# <a name="raw-pseudo-operations"></a>Unformatierte Pseudooperationen
In diesem Thema werden die Pseudooperationen aufgelistet.  
  
## <a name="remarks"></a>Hinweise  
  
|Pseudo-Vorgang|Beschreibung|  
|----------------------|-----------------|  
|PROC-FRAME [: Ehandler]|Ursachen MASM generiert eine Funktion Tabelleneintrag in .pdata und Entladen von Informationen im .xdata für eine Funktion der strukturierten Ausnahmebehandlung entladen Verhalten.  Wenn Ehandler vorhanden ist, wird diese Prozedur als der sprachspezifischer Handler in .xdata eingegeben.<br /><br /> Wenn der FRAME-Attribut verwendet wird, es muss darauf folgen ein. ENDPROLOG-Direktive.  Wenn die Funktion eine Endfunktion (gemäß Definition in [Funktionstypen](../build/function-types.md)) die FRAME-Attribut ist nicht erforderlich, wie die restlichen Pseudooperationen sind.|  
|. PUSHREG reg|Generiert einen UWOP_PUSH_NONVOL Entladung Code-Eintrag für die angegebene Registernummer mit dem aktuellen offset im Prolog.<br /><br /> Dies sollte nur mit permanentem Ganzzahlregister verwendet werden.  Für Pushbenachrichtigungen von volatile Register, verwendet ein. ALLOCSTACK 8, stattdessen|  
|. SETFRAME Reg, offset|Füllt das Registrieren Feld und einem festen Offset in die Entladung-Informationen, die mit dem angegebenen Register und Offset. Der Offset muss ein Vielfaches von 16 sein und kleiner oder gleich 240. Diese Direktive generiert außerdem einen UWOP_SET_FPREG Entladung Code-Eintrag für das angegebene Register mit den aktuellen Prologoffset.|  
|. ALLOCSTACK Größe|Generiert eine UWOP_ALLOC_SMALL oder einen UWOP_ALLOC_LARGE mit der angegebenen Größe für den aktuellen Offset im Prolog.<br /><br /> Die Größenoperand muss ein Vielfaches von 8 sein.|  
|. SAVEREG Reg, offset|Generiert einen UWOP_SAVE_NONVOL oder einen UWOP_SAVE_NONVOL_FAR Entladung Code-Eintrag für den angegebenen registrieren und einem festen Offset unter Verwendung der aktuellen Prolog Verschiebung. MASM wird die effizienteste Codierung auswählen.<br /><br /> Offset muss positiv und ein Vielfaches von 8 sein.  Offset ist relativ zu der Basis des Rahmens für die Prozedur, die im Allgemeinen RSP angibt, oder, wenn der Frame-Pointer, die nicht skalierten Frame-Pointer verwenden.|  
|. SAVEXMM128 Reg, offset|Generiert einen UWOP_SAVE_XMM128 oder einen UWOP_SAVE_XMM128_FAR Entladung Code-Eintrag für den angegebenen XMM-Register und einem festen Offset unter Verwendung der aktuellen Prolog Verschiebung. MASM wird die effizienteste Codierung auswählen.<br /><br /> Offset muss positiv und ein Vielfaches von 16 sein.  Offset ist relativ zu der Basis des Rahmens für die Prozedur, die im Allgemeinen RSP angibt, oder, wenn der Frame-Pointer, die nicht skalierten Frame-Pointer verwenden.|  
|. PUSHFRAME [Code]|Generiert einen UWOP_PUSH_MACHFRAME Entladung Codeeintrag an. Wenn der optionale Code angegeben wird, erhält der Entladung Codeeintrag einen 1-Modifizierer. Andernfalls wird der Modifizierer 0.|  
|.ENDPROLOG|Signalisiert das Ende der Prologdeklarationen.  Muss in die ersten 255 Byte der Funktion auftreten.|  
  
 Dies ist eine Beispiel-Funktionsprologs mit richtiger Verwendung der meisten Opcodes:  
  
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