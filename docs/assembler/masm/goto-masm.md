---
title: GOTO (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9eecdab2fe91de0aae656b37c6fddafe658e60c0
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
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