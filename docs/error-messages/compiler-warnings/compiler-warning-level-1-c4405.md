---
title: Compilerwarnung (Stufe 1) C4405 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4405
dev_langs:
- C++
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b20bde360df28158ad504739a1de10d90e3ef0cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4405"></a>Compilerwarnung (Stufe 1) C4405
'Bezeichner': Bezeichner ist ein reserviertes Wort  
  
 Ein Wort für die Inlineassembly reserviert wird als Name einer Variablen verwendet. Dies kann zu unvorhersehbaren Ergebnissen führen. Um diese Warnung zu beheben, vermeiden Sie Variablen mit Wörtern, die für die Inlineassembly reserviert. Im folgenden Beispiel wird C4405 generiert:  
  
```  
// C4405.cpp  
// compile with: /W1  
// processor: x86  
void func1() {  
   int mov = 0, i = 0;  
   _asm {  
      mov mov, 0;   // C4405  
      // instead, try ..  
      // mov i, 0;  
   }  
}  
  
int main() {  
}  
```