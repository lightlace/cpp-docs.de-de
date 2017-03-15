---
title: "Compilerwarnung (Stufe 3) C4334 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4334"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4334"
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 3) C4334
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Das Ergebnis der 32\-Bit\-Verschiebung wurde implizit in 64 Bits konvertiert. \(War eine 64\-Bit\-Verschiebung vorgesehen?\)  
  
 Das Ergebnis der 32\-Bit\-Verschiebung wurde implizit in 64 Bits konvertiert, und der Compiler geht davon aus, dass eine 64\-Bit\-Verschiebung vorgesehen war.  Verwenden Sie zur Behebung des Problems eine 64\-Bit\-Verschiebung, oder wandeln Sie das Ergebnis der Verschiebung explizit in 64 Bits um.  
  
## Beispiel  
 Im folgenden Beispiel wird C4334 generiert.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```