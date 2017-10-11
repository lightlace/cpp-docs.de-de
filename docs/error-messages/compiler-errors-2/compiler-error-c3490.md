---
title: Compilerfehler C3490 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 42923edc2d238e7f0b64858561f7d23d211abd80
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3490"></a>Compilerfehler C3490
"var" kann nicht geändert werden, da über ein Konstantenobjekt darauf zugegriffen wird  
  
 Ein Lambda-Ausdruck, der in einer `const` -Methode deklariert ist, kann nicht änderbare Memberdaten nicht ändern.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `const` -Modifizierer aus der Methodendeklaration.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3490 generiert, da die Membervariable `_i` in einer `const` -Methode geändert wird:  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3490 durch Entfernen des `const` -Modifizierers aus der Methodendeklaration aufgelöst:  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
