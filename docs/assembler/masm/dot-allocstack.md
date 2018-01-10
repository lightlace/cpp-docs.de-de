---
title: . ALLOCSTACK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .ALLOCSTACK
dev_langs: C++
helpviewer_keywords: .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20d9147b2c1a95d4fc9600935111a9c0c013be21
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="allocstack"></a>.ALLOCSTACK
Generiert eine **UWOP_ALLOC_SMALL** oder ein **UWOP_ALLOC_LARGE** mit der angegebenen Größe für den aktuellen Offset im Prolog.  
  
## <a name="syntax"></a>Syntax  
  
```  
.ALLOCSTACK size  
```  
  
## <a name="remarks"></a>Hinweise  
 MASM wird die effizienteste Codierung für eine bestimmte Größe auswählen.  
  
 . ALLOCSTACK ist nur zulässig, innerhalb der Prolog, die von erweitert und ermöglicht ml64.exe angeben, wie eine Funktion Frame entlädt die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren keine Code; Es werden nur generiert, `.xdata` und `.pdata`. . ALLOCSTACK sollte Anweisungen vorangestellt werden, die die Aktionen, entladen werden tatsächlich implementieren. Es wird empfohlen, die Direktiven entladen und der Code, den sie in einem Makro Entladung vorgesehen sind, um sicherzustellen, dass Vereinbarung zu umschließen.  
  
 Die `size` Operand muss ein Vielfaches von 8 sein.  
  
 Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="sample"></a>Beispiel  
 Das folgende Beispiel zeigt, wie einen Entladung/Ausnahmehandler angegeben wird:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)