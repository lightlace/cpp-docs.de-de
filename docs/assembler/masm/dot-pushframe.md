---
title: . PUSHFRAME | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .PUSHFRAME
dev_langs:
- C++
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66531207d21bb7e9e0c165db135f5a0c0d77e478
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
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