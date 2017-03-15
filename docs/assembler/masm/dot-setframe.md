---
title: ".SETFRAME"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - ".SETFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SETFRAME directive"
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# .SETFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Füllt das Feld und den Offset in den Entladeinformationen mit dem angegebenen Register \(`reg`\) und den Offset des Rahmens registers aus \(`offset`\).  Der Offset muss ein Vielfaches von 16 und kleiner oder gleich 240 sein.  Diese Direktive `UWOP_SET_FPREG` Entladecode generiert außerdem einen Eintrag für das angegebene Register mithilfe des aktuellen Offset vorläufige.  
  
## Syntax  
  
```  
.SETFRAME reg, offset  
```  
  
## Hinweise  
 .SETFRAME ml64.exe\-Benutzern kann, um anzugeben wie Entladungen eine Rahmenfunktion und ist nur innerhalb des Prologs zugelassen, die von der Deklaration [PROC](../../assembler/masm/proc.md) FRAME auf [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)\-Direktive erstreckt.  Diese Direktive kein Code generiert. generieren und `.xdata` nur `.pdata`.  .SETFRAME sollte von den Anweisungen vorangestellt werden, die eigentlich selbst implementieren die Aktionen zu entladen.  Es empfiehlt sich, die Entladungs Direktiven und den Code umschlossen werden, die sie impliziert werden, die in einem Makro entladen, um Vertrags sicherzustellen.  
  
 Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Beispiel  
  
### Beschreibung  
 Das folgende Beispiel zeigt, wie Sie einen Framezeiger verwendet:  
  
### Code  
  
```  
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
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)