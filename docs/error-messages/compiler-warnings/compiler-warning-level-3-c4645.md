---
title: Compilerwarnung (Stufe 3) C4645 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4645
dev_langs:
- C++
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718afb6b8336e36e0c0244cbdccd8af16ac4167f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4645"></a>Compilerwarnung (Stufe 3) C4645
Eine Funktion, die mit "__declspec(noreturn)" deklariert wurde, hat eine Rückgabeanweisung  
  
 A [return](../../cpp/return-statement-in-program-termination-cpp.md) -Anweisung wurde in einer Funktion gefunden, die mit dem [noreturn](../../cpp/noreturn.md) `__declspec` -Modifizierer gekennzeichnet ist. Die `return` -Anweisung wurde ignoriert.  
  
 Im folgenden Beispiel wird C4645 generiert:  
  
```  
// C4645.cpp  
// compile with:  /W3  
void __declspec(noreturn) func() {  
   return;   // C4645, delete this line to resolve  
}  
  
int main() {  
}  
```