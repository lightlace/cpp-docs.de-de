---
title: Compilerfehler C3487 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3487
dev_langs:
- C++
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 566f130e3d65826feecc02afae0cc1a7db335efe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3487"></a>Compilerfehler C3487
„Rückgabetyp“: Alle Rückgabeausdrücke müssen in denselben Typ hergeleitet werden: Zuvor war es „Rückgabetyp“.  
  
 Ein Lambdaausdruck muss seinen eigenen Rückgabetyp angeben, es sei denn, er enthält eine einzelne Rückgabeanweisung. Wenn ein Lambda-Ausdruck mehrere Rückgabeanweisungen enthält, müssen alle den gleichen Typ aufweisen.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Geben Sie einen nachgestellten Rückgabetyp für den Lambda-Ausdruck an. Stellen Sie sicher, dass alle Rückgaben vom Lambda denselben Typ aufweisen oder implizit zu diesem Rückgabetyp konvertiert werden können.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird „C3487“ generiert, da die Rückgabetypen vom Lambda nicht übereinstimmen.  
  
```  
// C3487.cpp  
// Compile by using: cl /c /W4 C3487.cpp  
  
int* test(int* pi) {  
   // To fix the error, uncomment the trailing return type below  
   auto odd_pointer = [=]() /* -> int* */ {  
      if (*pi % 2)   
         return pi;  
      return nullptr; // C3487 - nullptr is not an int* type  
   };  
   return odd_pointer();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)