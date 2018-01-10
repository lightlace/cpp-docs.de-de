---
title: Compilerfehler C3496 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3496
dev_langs: C++
helpviewer_keywords: C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8e5e441011c69e2b50b4565981d89a7730d542f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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