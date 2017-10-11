---
title: Funktionsaufruf (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C++ functions
- functions [C++], calling
- operator overloading [C++], function calls
- function overloading [C++], function-call operator
- function calls, operator
- operators [C++], overloading
- operator overloading [C++], examples
- function call operator ()
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e066ab4c154c04c0c1a39b7f8d0164881a0a96cc
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="function-call-c"></a>Funktionsaufruf (C++)
Der Funktionsaufrufoperator, aufgerufen unter Verwendung von Klammern, ist ein binärer Operator.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
primary-expression ( expression-list )  
```  
  
## <a name="remarks"></a>Hinweise  
 In diesem Kontext ist `primary-expression` der erste Operand, und `expression-list`, eine möglicherweise leere Liste von Argumenten, ist der zweite Operand. Der Funktionsaufrufoperator wird für Vorgänge verwendet, die eine Anzahl von Parametern benötigen. Dies funktioniert, da eine `expression-list` eine Liste und kein einzelner Operand ist. Der Funktionsaufrufoperator muss eine nicht statische Memberfunktion sein.  
  
 Wenn der Funktionsaufrufoperator überladen ist, ändert er nicht die Art und Weise, wie Funktionen aufgerufen werden. Er ändert vielmehr die Art und Weise, wie der Operator interpretiert werden muss, wenn er auf Objekte eines angegebenen Klassentyps angewendet wird. Der folgende Code etwa wäre normalerweise ohne Bedeutung:  
  
```  
Point pt;  
pt( 3, 2 );  
```  
  
 Bei einem entsprechenden überladenen Funktionsaufrufoperator kann jedoch diese Syntax verwendet werden, um die `x`-Koordinate um 3 Einheiten und die `y`-Koordinate um 2 Einheiten zu versetzen. Der folgende Code veranschaulicht eine solche Definition:  
  
```  
// function_call.cpp  
class Point  
{  
public:  
    Point() { _x = _y = 0; }  
    Point &operator()( int dx, int dy )  
        { _x += dx; _y += dy; return *this; }  
private:  
    int _x, _y;  
};  
  
int main()  
{  
   Point pt;  
   pt( 3, 2 );  
}  
```  
  
 Beachten Sie, dass der Funktionsaufrufoperator auf den Namen eines Objekts, nicht den Namen einer Funktion angewendet wird.  
  
 Sie können außerdem den Funktionsaufruf-Operator überladen und einen Zeiger auf eine Funktion verwenden (anstelle der eigentlichen Funktion).  
  
```cpp  
typedef void(*ptf)();  
void func()  
{  
}  
struct S  
{  
   operator ptf()  
   {  
      return func;  
   }  
};  
  
int main()  
{  
   S s;  
   s();//operates as s.operator ptf()()  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorüberladung](../cpp/operator-overloading.md)
