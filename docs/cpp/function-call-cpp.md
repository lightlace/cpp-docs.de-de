---
title: "Funktionsaufruf (C++)"
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
  - "Funktionsaufrufoperator ( )"
  - "Funktionsaufrufe, C++-Funktionen"
  - "Funktionsaufrufe, Operator"
  - "Funktionsüberladung, function-call-Operator"
  - "Funktionen [C++], Aufrufen"
  - "Operatoren überladen, Beispiele"
  - "Operatoren überladen, Funktionsaufrufe"
  - "Operatoren [C++], Überladen"
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionsaufruf (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Funktionsaufrufoperator, aufgerufen unter Verwendung von Klammern, ist ein binärer Operator.  
  
## Syntax  
  
```  
  
primary-expression ( expression-list )  
```  
  
## Hinweise  
 In diesem Kontext ist `primary-expression` der erste Operand, und `expression-list`, eine möglicherweise leere Liste von Argumenten, ist der zweite Operand.  Der Funktionsaufrufoperator wird für Vorgänge verwendet, die eine Anzahl von Parametern benötigen.  Dies funktioniert, da eine `expression-list` eine Liste und kein einzelner Operand ist.  Der Funktionsaufrufoperator muss eine nicht statische Memberfunktion sein.  
  
 Wenn der Funktionsaufrufoperator überladen ist, ändert er nicht die Art und Weise, wie Funktionen aufgerufen werden. Er ändert vielmehr die Art und Weise, wie der Operator interpretiert werden muss, wenn er auf Objekte eines angegebenen Klassentyps angewendet wird.  Der folgende Code etwa wäre normalerweise ohne Bedeutung:  
  
```  
Point pt;  
pt( 3, 2 );  
```  
  
 Bei einem entsprechenden überladenen Funktionsaufrufoperator kann jedoch diese Syntax verwendet werden, um die `x`\-Koordinate um 3 Einheiten und die `y`\-Koordinate um 2 Einheiten zu versetzen.  Der folgende Code veranschaulicht eine solche Definition:  
  
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
  
 Sie können außerdem den Funktionsaufruf\-Operator überladen und einen Zeiger auf eine Funktion verwenden \(anstelle der eigentlichen Funktion\).  
  
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
  
## Siehe auch  
 [Überladen von Operatoren](../cpp/operator-overloading.md)