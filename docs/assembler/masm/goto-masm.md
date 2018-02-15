---
title: GOTO (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c86a9b5bc83110f20dccf73f51b1e1aabc693db2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="goto-masm"></a>GOTO (MASM)
Überträgt die Assembly in die Zeile markiert **: *** Macrolabel*.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>Hinweise  
 **GOTO** ist zulässig, nur innerhalb der [MAKRO](../../assembler/masm/macro.md), [für](../../assembler/masm/for-masm.md), [FORC](../../assembler/masm/forc.md), [wiederholen](../../assembler/masm/repeat.md), und **beim**blockiert. Die Bezeichnung muss die einzige Anweisung in der Zeile sein und muss einen führenden Doppelpunkt vorangestellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)