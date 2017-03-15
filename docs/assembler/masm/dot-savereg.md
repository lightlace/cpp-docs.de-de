---
title: ".SAVEREG"
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
  - ".SAVEREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEREG directive"
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEREG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erzeugt entweder `UWOP_SAVE_NONVOL` oder einen Eintrag `UWOP_SAVE_NONVOL_FAR` Entladecode für das angegebene Register \(`reg`\(Offset\) und`offset`\) mithilfe des aktuellen Offset vorläufige.  Von MASM wird die effizienteste Codierung ausgewählt.  
  
## Syntax  
  
```  
.SAVEREG reg, offset  
```  
  
## Hinweise  
 .SAVEREG ml64.exe\-Benutzern kann, um anzugeben wie Entladungen eine Rahmenfunktion und ist nur innerhalb des Prologs zugelassen, die von der Deklaration [PROC](../../assembler/masm/proc.md) FRAME auf [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)\-Direktive erstreckt.  Diese Direktive kein Code generiert. generieren und `.xdata` nur `.pdata`.  .SAVEREG sollte von den Anweisungen vorangestellt werden, die eigentlich selbst implementieren die Aktionen zu entladen.  Es empfiehlt sich, die Entladungs Direktiven und den Code umschlossen werden, die sie impliziert werden, die in einem Makro entladen, um Vertrags sicherzustellen.  
  
 Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)