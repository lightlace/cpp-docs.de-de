---
title: "Inkrementierungs- und Dekrementierungsoperatoren überladen (C++) | Microsoft Docs"
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
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 432863fd2d1600ff0e82a69813c0513a32c56612
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="increment-and-decrement-operator-overloading-c"></a>Überladen von Inkrementierungs- und Dekrementierungsoperatoren (C++)
Die Inkrement- und Dekrementoperatoren gehören einer speziellen Kategorie an, da es jeweils zwei Varianten gibt:  
  
-   Präinkrement und Postinkrement  
  
-   Prädekrement und Postdekrement  
  
 Wenn Sie überladene Operator-Funktionen schreiben, kann es hilfreich sein, separate Versionen für die Präfix- und Postfix-Versionen dieser Operatoren zu implementieren. Um zwischen den beiden zu unterscheiden, wird die folgende Regel angewendet: Die Präfix-Form des Operators wird analog zu jedem anderen unären Operator deklariert. Die Postfix-Form akzeptiert ein zusätzliches Argument vom Typ `int`.  
  
> [!NOTE]
>  Wenn Sie einen überladenen Operator für die Postfix-Form des Inkrement- oder Dekrementoperators angeben, muss das zusätzliche Argument vom Typ `int` sein. Durch Angabe eines anderen Typs wird ein Fehler generiert.  
  
 Das folgende Beispiel zeigt, wie Präfix- und Postfix-Inkrement- und Dekrementoperatoren für die Klasse `Point` definiert werden:  
  
```  
// increment_and_decrement1.cpp  
class Point  
{  
public:  
   // Declare prefix and postfix increment operators.  
   Point& operator++();       // Prefix increment operator.  
   Point operator++(int);     // Postfix increment operator.  
  
   // Declare prefix and postfix decrement operators.  
   Point& operator--();       // Prefix decrement operator.  
   Point operator--(int);     // Postfix decrement operator.  
  
   // Define default constructor.  
   Point() { _x = _y = 0; }  
  
   // Define accessor functions.  
   int x() { return _x; }  
   int y() { return _y; }  
private:  
   int _x, _y;  
};  
  
// Define prefix increment operator.  
Point& Point::operator++()  
{  
   _x++;  
   _y++;  
   return *this;  
}  
  
// Define postfix increment operator.  
Point Point::operator++(int)  
{  
   Point temp = *this;  
   ++*this;  
   return temp;  
}  
  
// Define prefix decrement operator.  
Point& Point::operator--()  
{  
   _x--;  
   _y--;  
   return *this;  
}  
  
// Define postfix decrement operator.  
Point Point::operator--(int)  
{  
   Point temp = *this;  
   --*this;  
   return temp;  
}  
int main()  
{  
}  
```  
  
 Die gleichen Operatoren können im Dateigültigkeitsbereich (global) mit den folgenden Funktionsköpfen definiert werden:  
  
```  
friend Point& operator++( Point& )      // Prefix increment  
friend Point& operator++( Point&, int ) // Postfix increment  
friend Point& operator--( Point& )      // Prefix decrement  
friend Point& operator--( Point&, int ) // Postfix decrement  
```  
  
 Das Argument vom Typ `int`, dass die Postfix-Form des Inkrement- oder Dekrement-Operators kennzeichnet, wird im Allgemeinen nicht verwendet, um Argumente zu übergeben. Es enthält in der Regel den Wert 0. Es kann jedoch wie folgt verwendet werden:  
  
```  
// increment_and_decrement2.cpp  
class Int  
{  
public:  
    Int &operator++( int n );  
private:  
    int _i;  
};  
  
Int& Int::operator++( int n )  
{  
    if( n != 0 )    // Handle case where an argument is passed.  
        _i += n;  
    else  
        _i++;       // Handle case where no argument is passed.  
    return *this;  
}  
int main()  
{  
   Int i;  
   i.operator++( 25 ); // Increment by 25.  
}  
```  
  
 Es gibt keine Syntax für die Verwendung von Inkrement- oder Dekrementoperatoren, um diese Werte auf eine andere Weise zu übertragen als durch expliziten Aufruf, wie im vorangehenden Code dargestellt. Eine einfachere Möglichkeit, diese Funktionalität zu implementieren, besteht darin, den Hinzufügen-/Zuweisungsoperator (`+=`) zu überladen.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorüberladung](../cpp/operator-overloading.md)
