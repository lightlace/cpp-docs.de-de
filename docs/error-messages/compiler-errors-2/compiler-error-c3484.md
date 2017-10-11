---
title: Compilerfehler C3484 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3484
dev_langs:
- C++
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0ec019561a042b5dd5fd05aa8660bc8ff6b1d976
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3484"></a>Compilerfehler C3484
Vor dem Rückgabetyp wird '->' erwartet.  
  
 Sie müssen vor dem Rückgabetyp eines Lambdaausdrucks `->` bereitstellen.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie `->` vor dem Rückgabetyp bereit.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Fehler C3484 generiert:  
  
```  
// C3484a.cpp  
  
int main()  
{  
   return []() . int { return 42; }(); // C3484  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3484 durch Bereitstellen von `->` vor dem Rückgabetyp des Lambdaausdrucks behoben:  
  
```  
// C3484b.cpp  
  
int main()  
{  
   return []() -> int { return 42; }();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
