---
title: . IF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ab0e2fc510b4be8c5a9a8c0c3d0fb1c4347f0b9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053115"
---
# <a name="if"></a>.IF
Generiert Code, der testet `condition1` (z. B. AX 7 >) und führt die *Anweisungen* , wenn die Bedingung "true" ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   .IF condition1   
statements  
[[.ELSEIF condition2   
   statements]]  
[[.ELSE  
   statements]]  
.ENDIF  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine [. ELSE](../../assembler/masm/dot-else.md) folgt, die Anweisungen werden ausgeführt, wenn die ursprüngliche Bedingung "false" ist. Beachten Sie, dass die Bedingungen zur Laufzeit ausgewertet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)