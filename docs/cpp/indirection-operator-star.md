---
title: "Dereferenzierungsoperator: *"
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
  - "*-Operator"
  - "Dereferenzierungsoperator"
  - "Dereferenzierungsoperator, Syntax"
  - "Operatoren [C++], Dereferenzierung"
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Dereferenzierungsoperator: *
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
* cast-expression  
```  
  
## Hinweise  
 Der unäre Dereferenzierungsoperator \(**\***\) dereferenziert einen Zeiger, d. h. er konvertiert er einen Zeigerwert in einen l\-Wert.  Der Operand des Dereferenzierungsoperators muss ein Zeiger auf einen Typ sein.  Das Ergebnis des Dereferenzierungsausdrucks ist der Typ, aus dem der Zeigertyp abgeleitet wird.  Die Verwendung des **\***\-Operators in diesem Kontext unterscheidet sich von seiner Bedeutung als binärer Operator \(Multiplikation\).  
  
 Wenn der Operand auf eine Funktion verweist, ist das Ergebnis ein Funktionsbezeichner.  Wenn an einen Speicherort verwiesen wird, ist das Ergebnis ein l\-Wert, der den Speicherort festlegt.  
  
 Der Dereferenzierungsoperator kann kumulativ verwendet werden, um Zeiger zu Zeigern zu dereferenzieren.  Beispiel:  
  
```  
// expre_Indirection_Operator.cpp  
// compile with: /EHsc  
// Demonstrate indirection operator  
#include <iostream>  
using namespace std;  
int main() {  
   int n = 5;  
   int *pn = &n;  
   int **ppn = &pn;  
  
   cout  << "Value of n:\n"  
         << "direct value: " << n << endl  
         << "indirect value: " << *pn << endl  
         << "doubly indirect value: " << **ppn << endl  
         << "address of n: " << pn << endl  
         << "address of n via indirection: " << *ppn << endl;  
}  
```  
  
 Wenn der Zeigerwert ungültig ist, ist das Ergebnis nicht definiert.  Die folgende Liste umfasst einige der häufigsten Bedingungen, die einen Zeigerwert ungültig machen.  
  
-   Der Zeiger ist ein NULL\-Zeiger.  
  
-   Der Zeiger gibt die Adresse eines lokalen Elements an, das zum Zeitpunkt des Verweises nicht sichtbar ist.  
  
-   Der Zeiger gibt eine Adresse an, die nicht ordnungsgemäß auf den Objekttyp, auf den gezeigt wird, ausgerichtet ist.  
  
-   Der Zeiger gibt eine Adresse an, die nicht vom ausgeführten Programm verwendet wird.  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Address\-of\-Operator: &](../cpp/address-of-operator-amp.md)   
 [Dereferenzierungs\- und address\-of\-Operatoren](../c-language/indirection-and-address-of-operators.md)