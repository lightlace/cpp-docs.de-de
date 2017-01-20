---
title: ".ALLOCSTACK"
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
  - ".ALLOCSTACK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ALLOCSTACK directive"
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# .ALLOCSTACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert **UWOP\_ALLOC\_SMALL** oder **UWOP\_ALLOC\_LARGE** mit der angegebenen Größe während des aktuellen Offset im Prolog.  
  
## Syntax  
  
```  
.ALLOCSTACK size  
```  
  
## Hinweise  
 MASM wählt die effizienteste Codierung für eine angegebene Größe aus.  
  
 .ALLOCSTACK ml64.exe\-Benutzern kann, um anzugeben wie Entladungen eine Rahmenfunktion und ist nur innerhalb des Prologs zugelassen, die von der Deklaration [PROC](../../assembler/masm/proc.md) FRAME auf [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)\-Direktive erstreckt.  Diese Direktive kein Code generiert. generieren und `.xdata` nur `.pdata`.  .ALLOCSTACK sollte von den Anweisungen vorangestellt werden, die eigentlich selbst implementieren die Aktionen zu entladen.  Es empfiehlt sich, die Entladungs Direktiven und den Code umschlossen werden, die sie impliziert werden, die in einem Makro entladen, um Vertrags sicherzustellen.  
  
 Der `size` Operand muss ein Vielfaches von 8 sein.  
  
 Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine Entladung\/einen Ausnahmehandler angibt:  
  
```  
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
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)