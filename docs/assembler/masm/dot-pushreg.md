---
title: ".PUSHREG"
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
  - ".PUSHREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".PUSHREG directive"
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# .PUSHREG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert einen `UWOP_PUSH_NONVOL` Entladecode Registernummer für die angegebene Eintrag mit dem aktuellen Offset im Prolog.  
  
## Syntax  
  
```  
.PUSHREG register  
```  
  
## Hinweise  
 .PUSHREG zulässig ml64.exe\-Benutzern Entladungen, um anzugeben, wie eine Rahmenfunktion und ist nur innerhalb des Prologs zugelassen, die von der Deklaration [PROC](../../assembler/masm/proc.md) FRAME auf [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)\-Direktive erstreckt.  Diese Direktive kein Code generiert. generieren und `.xdata` nur `.pdata`.  .PUSHREG sollte von den Anweisungen vorangestellt werden, die eigentlich selbst implementieren die Aktionen zu entladen.  Es empfiehlt sich, die Entladungs Direktiven und den Code umschlossen werden, die sie impliziert werden, die in einem Makro entladen, um Vertrags sicherzustellen.  
  
 Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Beispiel  
  
### Beschreibung  
 Das folgende Beispiel zeigt, wie die nicht flüchtigen tegisters drückt.  
  
### Code  
  
```  
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
Example1 PROC FRAME  
   push r10  
.pushreg r10  
   push r15  
.pushreg r15  
   push rbx  
.pushreg rbx  
   push rsi  
.pushreg rsi  
.endprolog  
   ; rest of function ...  
   ret  
Example1 ENDP  
_text ENDS  
END  
```  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)