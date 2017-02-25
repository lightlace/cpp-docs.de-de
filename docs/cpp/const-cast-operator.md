---
title: "const_cast-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "const_cast"
  - "const_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_cast-Schlüsselwort [C++]"
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# const_cast-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Entfernt **const**, `volatile` und **\_\_unaligned**\-Attribute aus einer Klasse.  
  
## Syntax  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## Hinweise  
 Ein Zeiger auf einen beliebigen Objekttyp oder ein Zeiger auf einen Datenmember kann explizit in einen Typ konvertiert werden, der mit den Qualifizierern **const**, `volatile`\- und **\_\_unaligned** identisch ist.  Für Zeiger und Verweise verweist das Ergebnis auf das ursprüngliche Objekt.  Für Zeiger auf Datenmember, verweist das Ergebnis auf denselben Member wie der ursprüngliche \(uncast\) Zeiger auf Datenmember.  Je nach Typ des verweisenden Objekts, führt ein Schreibvorgang durch den resultierenden Zeiger, Verweis oder Zeiger auf Datenmember möglicherweise zu nicht definiertem Verhalten.  
  
 Sie können den Operator `const_cast` nicht verwenden, um den konstanten Status einer konstanten Variable direkt zu überschreiben.  
  
 Der Operator `const_cast` konvertiert einen NULL\-Zeigerwert in den NULL\-Zeigerwert des Zieltyps.  
  
## Beispiel  
  
```  
// expre_const_cast_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CCTest {  
public:  
   void setNumber( int );  
   void printNumber() const;  
private:  
   int number;  
};  
  
void CCTest::setNumber( int num ) { number = num; }  
  
void CCTest::printNumber() const {  
   cout << "\nBefore: " << number;  
   const_cast< CCTest * >( this )->number--;  
   cout << "\nAfter: " << number;  
}  
  
int main() {  
   CCTest X;  
   X.setNumber( 8 );  
   X.printNumber();  
}  
```  
  
 In der Zeile, die `const_cast` enthält, lautet der Datentyp des `this` Zeigers `const CCTest *`.  Der Operator `const_cast` ändert den Datentyp des `this`\-Zeigers in `CCTest *` und ermöglicht die Änderung des Members `number`.  Die Umwandlung erfolgt nur für den Rest der Anweisung, in der er angezeigt wird.  
  
## Siehe auch  
 [Umwandlungsoperatoren](../cpp/casting-operators.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)