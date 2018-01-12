---
title: . PUSHFRAME | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .PUSHFRAME
dev_langs: C++
helpviewer_keywords: .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c10a6b92be86b3b5fc30d2975cb60cf211b026f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pushframe"></a>.PUSHFRAME
Generiert eine `UWOP_PUSH_MACHFRAME` Einstiegspunkt Code entladen. Wenn das optionale `code` angegeben ist, wird der Eintrag der Entladung Code erhält einen 1-Modifizierer. Andernfalls wird der Modifizierer 0.  
  
## <a name="syntax"></a>Syntax  
  
```  
.PUSHFRAME [code]  
```  
  
## <a name="remarks"></a>Hinweise  
 . PUSHFRAME ist nur zulässig, innerhalb der Prolog, die von erweitert und ermöglicht ml64.exe angeben, wie eine Funktion Frame entlädt die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren keine Code; Es werden nur generiert, `.xdata` und `.pdata`. . PUSHFRAME sollte Anweisungen vorangestellt werden, die die Aktionen, entladen werden tatsächlich implementieren. Es wird empfohlen, die Direktiven entladen und der Code, den sie in einem Makro Entladung vorgesehen sind, um sicherzustellen, dass Vereinbarung zu umschließen.  
  
 Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)