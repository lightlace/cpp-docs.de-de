---
title: . SAVEXMM128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAVEXMM128
dev_langs: C++
helpviewer_keywords: .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4f79fc84e12f536383753d1d5982751cd30099d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="savexmm128"></a>.SAVEXMM128
Entweder generiert eine `UWOP_SAVE_XMM128` oder ein `UWOP_SAVE_XMM128_FAR` Entladen von Codeeintrag für den angegebenen XMM-Register und offset unter Verwendung der aktuellen Prolog Verschiebung. MASM wird die effizienteste Codierung auswählen.  
  
## <a name="syntax"></a>Syntax  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>Hinweise  
 . SAVEXMM128 ermöglicht Benutzern das ml64.exe angeben, wie eine Funktion Frame entlädt und ist nur zulässig, innerhalb der Prolog, die aus erweitert die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren keine Code; Es werden nur generiert, `.xdata` und `.pdata`. . SAVEXMM128 sollte Anweisungen vorangestellt werden, die die Aktionen, entladen werden tatsächlich implementieren. Es wird empfohlen, die Direktiven entladen und der Code, den sie in einem Makro Entladung vorgesehen sind, um sicherzustellen, dass Vereinbarung zu umschließen.  
  
 `offset`ein Vielfaches von 16 muss sein.  
  
 Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)