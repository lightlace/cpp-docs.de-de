---
title: ".SAVEXMM128"
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
  - ".SAVEXMM128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEXMM128 directive"
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEXMM128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erzeugt entweder `UWOP_SAVE_XMM128` , oder ein `UWOP_SAVE_XMM128_FAR` Eintrag Entladecode für das angegebene XMM\-Register und den angegebenen Offset mit dem aktuellen Prologoffset.  Von MASM wird die effizienteste Codierung ausgewählt.  
  
## Syntax  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## Hinweise  
 .SAVEXMM128 zulässig ml64.exe\-Benutzern Entladungen, um anzugeben, wie eine Rahmenfunktion und ist nur innerhalb des Prologs zugelassen, die von der Deklaration [PROC](../../assembler/masm/proc.md) FRAME auf [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)\-Direktive erstreckt.  Diese Direktive kein Code generiert. generieren und `.xdata` nur `.pdata`.  .SAVEXMM128 sollte von den Anweisungen vorangestellt werden, die eigentlich selbst implementieren die Aktionen zu entladen.  Es empfiehlt sich, die Entladungs Direktiven und den Code umschlossen werden, die sie impliziert werden, die in einem Makro entladen, um Vertrags sicherzustellen.  
  
 `offset` muss ein Vielfaches von 16 sein.  
  
 Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)