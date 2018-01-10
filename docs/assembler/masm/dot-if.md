---
title: . IF | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .IF
dev_langs: C++
helpviewer_keywords: .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2883ae63664248fdce054b39dd9291a6c1d7c431
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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