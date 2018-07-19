---
title: Compilerfehler C3493 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3493
dev_langs:
- C++
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3aec62bfff59396ec73141746193e4e3f16d84fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257315"
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