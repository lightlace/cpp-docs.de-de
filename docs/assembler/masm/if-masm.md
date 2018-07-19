---
title: IF (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76bf63b917a65a5a41fd261cfc861a77b0f0d16f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054002"
---
# <a name="if-masm"></a>IF (MASM)
Gewährt der Assembly *Ifstatements* Wenn *expression1* ist "true" (ungleich null) oder *Elseifstatements* Wenn *expression1* lautet "false" (0) und *expression2* ist "true".  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Direktiven können als Ersatz für [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, und **ELSEIFNDEF** . Optional, assembliert *Elsestatements* Wenn des vorherigen Ausdrucks "false" ist. Beachten Sie, dass die Assembly zum Zeitpunkt der Ausdrücke ausgewertet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)