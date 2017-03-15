---
title: "Address-of-Operator: &amp;"
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
  - "address-of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "&-Operator"
  - "&-Operator, address-of-Operator"
  - "address-of-Operator (&)"
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Address-of-Operator: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
& cast-expression  
```  
  
## Hinweise  
 Der unäre address\-of\-Operator \(**&**\) nimmt die Adresse seines Operanden an.  Bei dem Operand des address\-of\-Operators kann es sich entweder um einen Funktionsbezeichner oder einen l\-Wert handeln, der ein Objekt festgelegt, das kein Bitfeld ist und nicht mit dem **register**\-Speicherklassenspezifizierer deklariert wurde.  
  
 Der address\-of\-Operator kann nur auf Variablen vom Typ "Basis", "Struktur", "Klasse" oder "Union" angewendet werden, die auf Dateibereichsebene deklariert wurden, oder auf indizierte Arrayverweise.  In diesen Ausdrücken kann ein konstanter Ausdruck, der nicht den address\-of\-Operator einschließt, dem address\-of\-Ausdruck hinzugefügt oder von diesem subtrahiert werden.  
  
 Bei Anwendung auf Funktionen oder l\-Werte ist das Ergebnis des Ausdrucks ein Zeigertyp \(ein R\-Wert\), der vom Typ des Operanden abgeleitet wird.  Wenn beispielsweise der Operand vom Typ `char` ist, ist das Ergebnis des Ausdrucks ein Typzeiger auf `char`.  Der address\-of\-Operator, der auf **const**\- oder `volatile`\-Objekte angewendet wird, hat den Wert **const** `type` **\*** oder `volatile` `type` **\***, wobei `type` der Typ des ursprünglichen Objekts ist.  
  
 Wenn der address\-of Operator auf einen [qualifizierten Namen](assetId:///3fefb16d-8120-4627-8b3f-3d90fbdcd1df) angewendet wird, hängt das Ergebnis davon ab, ob *qualified\-name* einen statischen Member angibt.  Wenn dies der Fall ist, ist das Ergebnis ein Zeiger auf den Typ, der in der Deklaration des Members angegeben wird.  Wenn der Member nicht statisch ist, ist das Ergebnis ein Zeiger auf den Member *name* der Klasse, die von *qualified\-class\-name* angegeben wird. \(Weitere Informationen zu *qualified\-class\-name* erhalten Sie unter [Primäre Ausdrücke](../cpp/primary-expressions.md)\). Das folgende Codefragment zeigt, wie sich das Ergebnis unterscheidet, abhängig davon, ob der Member statisch ist.  
  
```  
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
           int   iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 In diesem Beispiel ergibt der Ausdruck `&PTM::fValue` den Typ `float *` anstelle von Typ `float PTM::*`, da `fValue` ein statischer Member ist.  
  
 Die Adresse einer überladenen Funktion kann nur verwendet werden, wenn klar ist, auf welche Version der Funktion verwiesen wird.  Weitere Informationen darüber, wie die Adresse einer bestimmten überladenen Funktion abgerufen wird, erhalten Sie unter [Adresse von überladenen Funktionen](../misc/address-of-overloaded-functions.md).  
  
 Die Anwendung des address\-of\-Operators auf einen Referenztyp führt zum gleichen Ergebnis wie die Anwendung des Operators auf das Objekt, an das der Verweis gebunden ist.  Beispiel:  
  
## Beispiel  
  
```  
// expre_Address_Of_Operator2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   double d;        // Define an object of type double.  
   double& rd = d;  // Define a reference to the object.  
  
   // Obtain and compare their addresses  
   if( &d == &rd )  
      cout << "&d equals &rd" << endl;  
}  
```  
  
## Ausgabe  
  
```  
&d equals &rd  
```  
  
 Im folgenden Beispiel wird der address\-of\-Operator benutzt, um ein Zeigerargument an eine Funktion zu übergeben:  
  
```  
// expre_Address_Of_Operator3.cpp  
// compile with: /EHsc  
// Demonstrate address-of operator &  
  
#include <iostream>  
using namespace std;  
  
// Function argument is pointer to type int  
int square( int *n ) {  
   return (*n) * (*n);  
}  
  
int main() {  
   int mynum = 5;  
   cout << square( &mynum ) << endl;   // pass address of int  
}  
```  
  
## Ausgabe  
  
```  
25  
```  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Lvalue\-Verweisdeklarator: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Dereferenzierungs\- und address\-of\-Operatoren](../c-language/indirection-and-address-of-operators.md)