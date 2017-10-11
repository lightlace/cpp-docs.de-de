---
title: Compilerfehler C3493 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3493
dev_langs:
- C++
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d2336caee3cf2eac6ee748bf40c8cd3f8bf871c2
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3493"></a>Compilerfehler C3493
"var" kann nicht implizit erfasst werden, da kein Standarderfassungsmodus angegeben wurde  
  
 Die leere Lambdaausdruckerfassung, `[]`, gibt an, dass der Lambdaausdruck weder explizit noch implizit Variablen erfasst.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Geben Sie einen Standarderfassungsmodus an, oder  
  
-   erfassen Sie explizit mindestens eine Variable.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3493 generiert, da eine externe Variable geändert, aber die leere Erfassungsklausel angegeben wird:  
  
```  
// C3493a.cpp  
  
int main()  
{  
   int m = 55;  
   [](int n) { m = n; }(99); // C3493  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3493 aufgelöst, indem die Erfassung nach Verweis als Standarderfassungsmodus angegeben wird.  
  
```  
// C3493b.cpp  
  
int main()  
{  
   int m = 55;  
   [&](int n) { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
