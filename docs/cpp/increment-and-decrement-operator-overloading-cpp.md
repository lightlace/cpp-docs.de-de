---
title: "&#220;berladen von Inkrementierungs- und Dekrementierungsoperatoren (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dekrementoperatoren"
  - "Dekrementoperatoren, Typen"
  - "Inkrementoperatoren"
  - "Inkrementoperatoren, Typen"
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berladen von Inkrementierungs- und Dekrementierungsoperatoren (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Inkrement\- und Dekrementoperatoren gehören einer speziellen Kategorie an, da es jeweils zwei Varianten gibt:  
  
-   Präinkrement und Postinkrement  
  
-   Prädekrement und Postdekrement  
  
 Wenn Sie überladene Operator\-Funktionen schreiben, kann es hilfreich sein, separate Versionen für die Präfix\- und Postfix\-Versionen dieser Operatoren zu implementieren.  Um zwischen den beiden zu unterscheiden, wird die folgende Regel angewendet: Die Präfix\-Form des Operators wird analog zu jedem anderen unären Operator deklariert. Die Postfix\-Form akzeptiert ein zusätzliches Argument vom Typ `int`.  
  
> [!NOTE]
>  Wenn Sie einen überladenen Operator für die Postfix\-Form des Inkrement\- oder Dekrementoperators angeben, muss das zusätzliche Argument vom Typ `int` sein. Durch Angabe eines anderen Typs wird ein Fehler generiert.  
  
 Das folgende Beispiel zeigt, wie Präfix\- und Postfix\-Inkrement\- und Dekrementoperatoren für die Klasse `Point` definiert werden:  
  
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
  
 Die gleichen Operatoren können im Dateigültigkeitsbereich \(global\) mit den folgenden Funktionsköpfen definiert werden:  
  
```  
friend Point& operator++( Point& )      // Prefix increment  
friend Point& operator++( Point&, int ) // Postfix increment  
friend Point& operator--( Point& )      // Prefix decrement  
friend Point& operator--( Point&, int ) // Postfix decrement  
```  
  
 Das Argument vom Typ `int`, dass die Postfix\-Form des Inkrement\- oder Dekrement\-Operators kennzeichnet, wird im Allgemeinen nicht verwendet, um Argumente zu übergeben.  Es enthält in der Regel den Wert 0.  Es kann jedoch wie folgt verwendet werden:  
  
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
  
 Es gibt keine Syntax für die Verwendung von Inkrement\- oder Dekrementoperatoren, um diese Werte auf eine andere Weise zu übertragen als durch expliziten Aufruf, wie im vorangehenden Code dargestellt.  Eine einfachere Möglichkeit, diese Funktionalität zu implementieren, besteht darin, den Hinzufügen\-\/Zuweisungsoperator \(`+=`\) zu überladen.  
  
## Siehe auch  
 [Überladen von Operatoren](../cpp/operator-overloading.md)