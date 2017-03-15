---
title: ".ENDPROLOG"
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
  - ".ENDPROLOG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ENDPROLOG directive"
ms.assetid: 61a2474c-9527-46e6-9f9d-bc4b42c10f35
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# .ENDPROLOG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Signalisiert das Ende der Prologdeklarationen.  
  
## Syntax  
  
```  
.ENDPROLOG  
```  
  
## Hinweise  
 Es ist ein Fehler, um vorläufige einer der Deklarationen außerhalb des Bereichs zwischen [PROC](../../assembler/masm/proc.md) FRAME und .ENDPROLOG zu verwenden.  
  
 Weitere Informationen finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)