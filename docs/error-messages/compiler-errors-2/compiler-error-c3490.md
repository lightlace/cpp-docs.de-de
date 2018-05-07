---
title: Compilerfehler C3490 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 593e5509ada926f27243a761da3470eb2d846a22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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