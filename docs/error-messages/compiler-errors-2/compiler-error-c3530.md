---
title: Compilerfehler C3530 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0d66e76fc3e44a037f52aa6e217fae848f1338d2
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3530"></a>Compilerfehler C3530
'Auto' kann nicht mit einem anderen Typspezifizierer kombiniert werden  
  
 Ein Typspezifizierer wird verwendet, mit dem `auto` Schlüsselwort.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verwenden Sie keinen Typspezifizierer in einer Variablendeklaration, die mithilfe der `auto` Schlüsselwort.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel wird C3530 erzeugt, da Variable `x` wird deklariert, mit der `auto` -Schlüsselwort und Datentyp `int`, und da im Beispiel mit kompiliert wird **/Zc: Auto**.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)
