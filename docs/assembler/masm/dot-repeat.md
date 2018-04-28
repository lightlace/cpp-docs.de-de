---
title: . WIEDERHOLEN SIE DIE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .REPEAT
dev_langs:
- C++
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41e3dadaa95cb4bf0ca4a17af32332d5b5471245
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="repeat"></a>.REPEAT
Generiert Code, durch die Ausführung des Blocks des wiederholt *Anweisungen* bis `condition` wird "true". [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md), die "true" wird, wenn CX NULL ist, kann als Ersatz für [. BIS](../../assembler/masm/dot-until.md). Die `condition` ist optional mit **. UNTILCXZ**.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)