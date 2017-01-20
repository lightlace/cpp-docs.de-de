---
title: "Operatoren f&#252;r den Memberzugriff: . und -&gt;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "."
  - "->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ". Operator"
  - "->-Operator"
  - "Punktoperator (.)"
  - "Memberzugriff"
  - "Memberzugriff, Ausdrücke"
  - "Memberzugriff, Operatoren"
  - "Operatoren [C++], Memberzugriff"
  - "Postfixoperatoren"
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Operatoren f&#252;r den Memberzugriff: . und -&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
      postfix-expression   
      . name  
postfix-expression –> name  
```  
  
## Hinweise  
 Die Memberzugriffsoperatoren **.** und **\-\>** verweisen auf Member von Strukturen, Unions und Klassen.  Memberzugriffsausdrücke haben den Wert und Typ des ausgewählten Members.  
  
 Es gibt zwei Arten von Memberzugriffsausdrücken:  
  
1.  In der ersten Form stellt *postfix\-expression* einen Wert vom Typ "struct", "class" oder "union" dar, und *name* gibt den Namen eines Members der angegebenen Struktur, Union oder Klasse an.  Der Wert des Vorgangs entspricht *name* und ist ein I\-Wert, wenn *postfix\-expression* ein I\-Wert ist.  
  
2.  In der zweiten Form stellt *postfix\-expression* einen Zeiger auf eine Struktur, Union oder Klasse dar, und *name* gibt den Namen eines Members der angegebenen Struktur, Union oder Klasse an.  Der Wert ist ein I\-Wert und entspricht *name*.  Der Operator **–\>** dereferenziert den Zeiger.  Daher führen die Ausdrücke *e***–\>**`member` und **\(\****e***\)**.`member` \(wobei *e* einen Zeiger darstellt\) zu identischen Ergebnissen \(außer wenn die Operatoren **–\>** oder **\*** überladen werden\).  
  
## Beispiel  
 Im folgenden Beispiel werden beide Formen des Memberzugriffsoperators dargestellt.  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
  **2\/1\/1900**  
**2\/1\/2000**   
## Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)   
 [Struktur\- und Unionmember](../c-language/structure-and-union-members.md)