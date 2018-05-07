---
title: Compilerwarnung (Stufe 1) C4401 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4401
dev_langs:
- C++
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8b8a7a2bced261bbff09422c3dfa6454061f636
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4401"></a>Compilerwarnung (Stufe 1) C4401
"Bitfeld": Schnittstellenmember Bitfeld ist.  
  
 Inline-Assemblycode versucht, einen Bitfeld Member zuzugreifen. Inlineassembly kann nicht Bitfeldmember, zugreifen, damit die letzte Ausrichtungsgrenze vor dem Bitfeld Element verwendet wird.  
  
 Um diese Warnung zu vermeiden, wandeln Sie das Bitfeld in einen geeigneten Typ, bevor Sie den Verweis in Inline-Assemblycode vornehmen. Im folgenden Beispiel wird C4401 generiert:  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```