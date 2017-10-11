---
title: Compilerfehler C3496 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 86c80c4b708bd4315b2ce2ceaf7b61e0629a8b2e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3496"></a>Compilerfehler C3496
"this" wird immer nach Wert erfasst: "&" wird ignoriert.  
  
 Der `this` -Zeiger kann nicht als Verweis erfasst werden.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Erfassen Sie den `this` -Zeiger nach Wert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3496 generiert, weil ein Verweis auf den `this` -Zeiger in der Erfassungsliste eines Lambdaausdrucks auftritt:  
  
```  
// C3496.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      [&this] {}(); // C3496  
   }  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
