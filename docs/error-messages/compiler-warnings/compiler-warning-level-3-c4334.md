---
title: Compilerwarnung (Stufe 3) C4334 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4334
dev_langs: C++
helpviewer_keywords: C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7218caa399aec0bd1b9755fb6d0942991732121e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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