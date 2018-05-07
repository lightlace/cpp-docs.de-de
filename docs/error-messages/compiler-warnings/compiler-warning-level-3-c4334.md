---
title: Compilerwarnung (Stufe 3) C4334 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f26749c968c3cac18b509046633ba3d91d15a4be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4334"></a>Compilerwarnung (Stufe 3) C4334
'Operator': Ergebnis der 32-Bit-Verschiebung implizit zu 64 Bit konvertiert (war ein 64-Bit-Verschiebung vorgesehen?)  
  
 Das Ergebnis des 32-Bit-Verschiebung wurde implizit konvertiert, 64-Bit, und der Compiler vermutet, dass es sich bei eine 64-Bit-Verschiebung vorgesehen war.  Zur Behebung des Problems, verwenden Sie 64-Bit-Verschiebung zu, oder wandeln Sie explizit das Ergebnis der Verschiebung auf 64-Bit.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4334 generiert.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```