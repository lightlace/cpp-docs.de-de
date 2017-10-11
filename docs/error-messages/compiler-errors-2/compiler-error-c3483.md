---
title: Compilerfehler C3483 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 145e0162c47b360b9d37cf95b108446f919435de
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
