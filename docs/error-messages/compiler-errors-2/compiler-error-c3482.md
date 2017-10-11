---
title: Compilerfehler C3482 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b19769a8a326613401263fa7700b85c36a9dbbe1
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3482"></a>Compilerfehler C3482
"this" kann nur als Lambdaerfassung innerhalb einer nicht statischen Memberfunktion verwendet werden.  
  
 Sie können `this` nicht an die Erfassungsliste eines Lambdaausdrucks übergeben, der in einer statischen Methode oder globalen Funktion deklariert ist.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Konvertieren Sie die einschließende Funktion in eine nicht statische Methode oder  
  
-   Entfernen Sie den `this` -Zeiger aus der Erfassungsliste des Lambdaausdrucks.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Fehler C3482 generiert:  
  
```  
// C3482.cpp  
// compile with: /c  
  
class C  
{  
public:  
   static void staticMethod()  
   {  
      [this] {}(); // C3482  
   }  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
