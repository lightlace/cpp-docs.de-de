---
title: "Additive Operatoren: + und -"
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
  - "-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "--Operator, Additive Operatoren in C++"
  - "+-Operator, Additive Operatoren"
  - "Additive Operatoren"
  - "Arithmetische Operatoren [C++], Additive Operatoren"
  - "Operatoren [C++], Addition"
  - "Subtraktionsoperator, Additive Operatoren"
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Additive Operatoren: + und -
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
expression + expression   
expression – expression  
```  
  
## Hinweise  
 Die additiven Operatoren sind:  
  
-   Addition \(**\+**\)  
  
-   Subtraktion \(**–**\)  
  
 Diese binären Operatoren weisen eine Assoziativität von links nach rechts auf.  
  
 Die additiven Operatoren nehmen Operanden der arithmetischen Operatoren oder Zeigertypen.  Das Ergebnis des Additionsoperators \(**\+**\) ist die Summe der Operanden.  Das Ergebnis des Subtraktionsoperators \(**–**\) ist die Differenz zwischen den Operanden.  Wenn einer oder beide der Operanden Zeiger sind, müssen sie Zeiger auf Objekte, nicht auf Funktionen sein.  Wenn beide Operanden Zeiger sind, sind die Ergebnisse nicht aussagekräftig, wenn nicht beide Zeiger auf Objekte im selben Array verweisen.  
  
 Additive Operatoren nehmen Operanden vom Typ *Arithmetisch*, *Ganzzahlig* und *Skalarwert*.  Diese sind in der folgenden Tabelle definiert.  
  
### Mit additiven Operatoren verwendete Typen  
  
|Typ|Bedeutung|  
|---------|---------------|  
|*Arithmetisch*|Ganzzahlige und nicht verankerte Typen werden kollektiv als "arithmetische" Typen bezeichnet.|  
|*Ganzzahlig*|Die Typen "char" und "int" in sämtlichen Größen \("long", "short"\) und Enumerationen sind ganzzahlige Typen.|  
|*Skalarwert*|Skalare Operanden sind entweder arithmetische oder Zeiger\-Operanden.|  
  
 Die gültigen Kombinationen für diese Operatoren sind:  
  
 *Arithmetisch* \+ *Arithmetisch*  
  
 *Skalarwert* \+ *Ganzzahlig*  
  
 *Ganzzahlig* \+ *Skalarwert*  
  
 *Arithmetisch* – *Arithmetisch*  
  
 *Skalarwert* – *Skalarwert*  
  
 Beachten Sie, dass Addition und Subtraktion keine äquivalenten Vorgänge sind.  
  
 Wenn beide Operanden arithmetisch sind, werden die Konvertierungen, die in [Arithmetische Konvertierungen](../misc/arithmetic-conversions.md) behandelt werden, auf die Operanden angewendet, und das Ergebnis besitzt den konvertierten Typ.  
  
## Beispiel  
  
```  
// expre_Additive_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
#define SIZE 5  
using namespace std;  
int main() {  
   int i = 5, j = 10;  
   int n[SIZE] = { 0, 1, 2, 3, 4 };  
   cout  << "5 + 10 = " << i + j << endl  
         << "5 - 10 = " << i - j << endl;  
  
   // use pointer arithmetic on array  
  
   cout << "n[3] = " << *( n + 3 ) << endl;  
}  
```  
  
## Zeigeraddition  
 Wenn einer der Operanden in einer Addition ein Zeiger auf ein Array von Objekten ist, muss der andere einen ganzzahligen Typ besitzen.  Das Ergebnis ist ein Zeiger, der vom selben Typ wie der ursprüngliche Zeiger ist und auf ein anderes Arrayelement zeigt.  Das folgende Codefragment veranschaulicht dieses Konzept:  
  
```  
short IntArray[10]; // Objects of type short occupy 2 bytes  
short *pIntArray = IntArray;  
  
for( int i = 0; i < 10; ++i )  
{  
    *pIntArray = i;  
    cout << *pIntArray << "\n";  
    pIntArray = pIntArray + 1;  
}  
```  
  
 Obwohl der Ganzzahlwert 1 zu `pIntArray` addiert wird, bedeutet dies nicht "1 zur Adresse addieren", sondern vielmehr "den Zeiger auf das nächste Objekt im Array richten", das 2 Bytes weiter ist \(oder `sizeof( int )`\).  
  
> [!NOTE]
>  Code in Form von `pIntArray = pIntArray + 1` ist in C\+\+\-Programmen selten. Um ein Inkrement auszuführen, werden diese Formen bevorzugt: `pIntArray++` oder `pIntArray += 1`.  
  
## Zeigersubtraktion  
 Wenn beide Operanden Zeiger sind, ist das Ergebnis der Subtraktion die Differenz \(in Arrayelementen\) zwischen den Operanden.  Der Subtraktionsausdruck gibt ein ganzzahliges Ergebnis mit Vorzeichen vom Typ ptrdiff\_t \(definiert in der Standardincludedatei STDDEF.H\) zurück.  
  
 Einer der Operanden kann vom ganzzahligen Typ sein, solange er der zweite Operand ist.  Das Ergebnis der Subtraktion ist vom selben Datentyp wie der ursprüngliche Zeiger.  Der Wert der Subtraktion ist ein Zeiger auf das *n* \(\) – *i*\-te Arrayelement. Dabei ist *n* das Element, auf das der ursprüngliche Zeiger verweist, und *i* ist der ganzzahlige Wert des zweiten Operanden.  
  
## Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Addition von Zeigertypen](../misc/addition-of-pointer-types.md)   
 [Subtraktion von Zeigertypen](../misc/subtraction-of-pointer-types.md)   
 [C\-Operatoren \(additiv\)](../c-language/c-additive-operators.md)