---
title: Compilerfehler C3483 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2605674ff701f70f7be6ea1b4158c9f8f0c6ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3483"></a>Compilerfehler C3483
"Variable" ist bereits Teil der Lambdaerfassungsliste.  
  
 Sie haben dieselbe Variable mehrmals an die Erfassungsliste eines Lambdaausdrucks übergeben.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie alle zusätzlichen Instanzen der Variablen aus der Erfassungsliste.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3483 generiert, da die Variable `n` mehrmals in der Erfassungsliste des Lambdaausdrucks vorkommt:  
  
```  
// C3483.cpp  
  
int main()  
{  
   int m = 6, n = 5;  
   [m,n,n] { return n + m; }(); // C3483  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)