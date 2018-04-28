---
title: . SAVEREG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEREG
dev_langs:
- C++
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a50b7a91efd7069e148222d3e3da44178974d6ba
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="savereg"></a>.SAVEREG
Erzeugt entweder eine `UWOP_SAVE_NONVOL` oder eine `UWOP_SAVE_NONVOL_FAR` Einstiegspunkt für das angegebene Register Code Entladen (`reg`) und Offset (`offset`) unter Verwendung der aktuellen Prolog Verschiebung. MASM wird die effizienteste Codierung auswählen.  
  
## <a name="syntax"></a>Syntax  
  
```  
.SAVEREG reg, offset  
```  
  
## <a name="remarks"></a>Hinweise  
 . SAVEREG ist nur zulässig, innerhalb der Prolog, die von erweitert und ermöglicht ml64.exe angeben, wie eine Funktion Frame entlädt die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren keine Code; Es werden nur generiert, `.xdata` und `.pdata`. . SAVEREG sollte Anweisungen vorangestellt werden, die die Aktionen, entladen werden tatsächlich implementieren. Es wird empfohlen, die Direktiven entladen und der Code, den sie in einem Makro Entladung vorgesehen sind, um sicherzustellen, dass Vereinbarung zu umschließen.  
  
 Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)