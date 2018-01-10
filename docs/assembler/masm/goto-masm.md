---
title: GOTO (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: goto
dev_langs: C++
helpviewer_keywords: GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed7e20bb7f81b74a2f670e604e958ca02f132531
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="goto-masm"></a>GOTO (MASM)
Überträgt die Assembly in die Zeile markiert **:***Macrolabel*.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>Hinweise  
 **GOTO** ist zulässig, nur innerhalb der [MAKRO](../../assembler/masm/macro.md), [für](../../assembler/masm/for-masm.md), [FORC](../../assembler/masm/forc.md), [wiederholen](../../assembler/masm/repeat.md), und **beim**blockiert. Die Bezeichnung muss die einzige Anweisung in der Zeile sein und muss einen führenden Doppelpunkt vorangestellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)