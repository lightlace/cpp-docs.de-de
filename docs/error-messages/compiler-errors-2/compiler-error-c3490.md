---
title: Compilerfehler C3490 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 83a215b1c4883ba7ed4b285af8c4efafe2cfaa05
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-error-c3490"></a>Compilerfehler C3490
"var" kann nicht geändert werden, da über ein Konstantenobjekt darauf zugegriffen wird  
  
 Ein Lambda-Ausdruck, der in einer `const` -Methode deklariert ist, kann nicht änderbare Memberdaten nicht ändern.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `const` -Modifizierer aus der Methodendeklaration.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3490 generiert, da es sich um die Membervariable ändert `_i` in einem `const` Methode:  
  
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
