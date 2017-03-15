---
title: "Unformatierte Pseudooperationen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Unformatierte Pseudooperationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden die Pseudooperationen aufgelistet.  
  
## Hinweise  
  
|Pseudooperation|Beschreibung|  
|---------------------|------------------|  
|PROC FRAME \[:ehandler\]|Veranlasst MASM, einen Funktionstabelleneintrag in .pdata und Entladeinformationen in .xdata für das Entladeverhalten bei der strukturierten Ausnahmebehandlung zu erzeugen.  Wenn ehandler vorhanden ist, wird dieser proc als sprachspezifischer Handler in .xdata eingetragen.<br /><br /> Wenn das FRAME\-Attribut verwendet wird, muss ihm eine .ENDPROLOG\-Direktive folgen.  Wenn die Funktion eine Endfunktion \(wie in [Funktionstypen](../build/function-types.md) definiert\) ist, werden das FRAME\-Attribut und die übrigen Pseudooperationen nicht benötigt.|  
|.PUSHREG reg|Erzeugt einen UWOP\_PUSH\_NONVOL\-Entladecodeeintrag für die angegebene Registernummer mit dem aktuellen Offset im Prolog.<br /><br /> Dies sollte nur bei nicht flüchtigen Ganzzahlregistern verwendet werden.  Verwenden Sie für push\-Anweisungen flüchtiger Register stattdessen einen .ALLOCSTACK 8.|  
|.SETFRAME reg, Offset|Füllt das Frameregisterfeld und den Offset in den Entladeinformationen mit den angegebenen Registern und Offsets.  Der Offset muss ein Vielfaches von 16 und kleiner oder gleich 240 sein.  Diese Direktive generiert auch einen UWOP\_SET\_FPREG\-Entladecodeeintrag für das angegebene Register mit dem aktuellen Prologoffset.|  
|.ALLOCSTACK Größe|Erzeugt einen UWOP\_ALLOC\_SMALL oder einen UWOP\_ALLOC\_LARGE mit der angegebenen Größe für den aktuellen Offset im Prolog.<br /><br /> Der Größenoperand muss ein Vielfaches von 8 sein.|  
|.SAVEREG reg, Offset|Erzeugt entweder einen UWOP\_SAVE\_NONVOL\- oder einen UWOP\_SAVE\_NONVOL\_FAR\-Entladecodeeintrag für das angegebene Register und den angegebenen Offset mit dem aktuellen Prologoffset.  Von MASM wird die effizienteste Codierung ausgewählt.<br /><br /> Der Offset muss positiv und ein Vielfaches von 8 sein.  Der Offset bezieht sich auf die Basis des Prozedurrahmens, der sich im Allgemeinen in RSP oder bei Verwendung eines Framezeigers im unskalierten Framezeiger befindet.|  
|.SAVEXMM128 reg, Offset|Erzeugt entweder einen UWOP\_SAVE\_XMM128\- oder einen UWOP\_SAVE\_XMM128\_FAR\-Entladecodeeintrag für das angegebene XXM\-Register und den angegebenen Offset mit dem aktuellen Prologoffset.  Von MASM wird die effizienteste Codierung ausgewählt.<br /><br /> Der Offset muss positiv und ein Vielfaches von 16 sein.  Der Offset bezieht sich auf die Basis des Prozedurrahmens, der sich im Allgemeinen in RSP oder bei Verwendung eines Framezeigers im unskalierten Framezeiger befindet.|  
|.PUSHFRAME \[Code\]|Erzeugt einen UWOP\_PUSH\_MACHFRAME\-Entladecodeeintrag.  Wenn der optionale Code angegeben wird, erhält der Entladecodeeintrag den Modifizierer 1.  Andernfalls ist der Modifizierer 0.|  
|.ENDPROLOG|Signalisiert das Ende der Prologdeklarationen.  Muss in den ersten 255 Byte der Funktion auftreten.|  
  
 Im Folgenden finden Sie ein Beispielfunktionsprolog mit richtiger Verwendung der meisten Opcodes:  
  
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
  
## Siehe auch  
 [Entladehilfen für MASM](../build/unwind-helpers-for-masm.md)