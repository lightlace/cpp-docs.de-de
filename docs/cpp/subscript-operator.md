---
title: "Tiefgestellt-Operator:"
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
  - "[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operatoren [C++], tiefgestellt"
  - "Postfixoperatoren"
  - "[]-Operator"
  - "Tiefgestellt-Operator, Syntax"
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Tiefgestellt-Operator:
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
postfix-expression [ expression ]  
```  
  
## Hinweise  
 Ein Postfixausdruck \(der auch ein primärer Ausdruck sein kann\), gefolgt von dem Indexoperator **\[ \]**, gibt eine Arrayindizierung an.  
  
 Weitere Informationen zu verwalteten Arrays finden Sie unter [Arrays](../windows/arrays-cpp-component-extensions.md).  
  
 Normalerweise ist der von *postfix\-expression* dargestellte Wert ein Zeigerwert, z. B. ein Arraybezeichner, und *expression* ist ein Ganzzahlwert \(einschließlich Enumerationstypen\).  Syntaktisch erforderlich ist allerdings nur, dass einer der Ausdrücke vom Zeigertyp und der andere Ausdruck vom Ganzzahltyp ist.  Daher kann der ganzzahlige Wert an der *postfix\-expression*\-Position sein, und der Zeigerwert kann in eckigen Klammern an der *expression*\- oder der "Index"\-Position sein.  Betrachten Sie das folgende Codefragment:  
  
```  
int nArray[5] = { 0, 1, 2, 3, 4 };  
cout << nArray[2] << endl;            // prints "2"  
cout << 2[nArray] << endl;            // prints "2"  
```  
  
 Im vorherigen Beispiel ist der Ausdruck `nArray[2]` identisch mit dem Ausdruck `2[nArray]`.  Der Grund dafür: Das Ergebnis eines Indexausdrucks *e1***\[** *e2* **\]** wird angegeben durch:  
  
 **\*\( \(** *e2* **\)** *\+* **\(***e1***\) \)**  
  
 Die Adresse, die durch den Ausdruck ausgegeben wird, entspricht nicht *e2*\-Bytes aus der Adresse *e1*.  Stattdessen wird die Adresse skaliert, um das nächste Objekt im Array *e2* zu erhalten.  Zum Beispiel:  
  
```  
double aDbl[2];  
```  
  
 Die Adressen von `aDb[0]` und `aDb[1]` sind 8 Bytes auseinander. Dies ist die Größe eines Objekts vom Typ **double**.  Diese Skalierung nach Objekttyp wird von der Programmiersprache C\+\+ automatisch ausgeführt und wird im Thema [Additive Operatoren](../cpp/additive-operators-plus-and.md) definiert, in dem Addition und Subtraktion von Operanden des Zeigertyps erläutert werden.  
  
 Ein indexierte Ausdruck kann auch mehrere Indizes haben, wie folgt:  
  
 *expression1* **\[***expression2***\] \[***expression3***\]**...  
  
 indexierte Ausdrücke sind von links nach rechts angeordnet.  Der äußerste linke indexierte Ausdruck *expression1***\[***expression2***\]** wird zuerst ausgewertet.  Die Adresse, die sich aus dem Hinzufügen von *expression1* und *expression2* ergibt, bildet einen Zeigerausdruck. Dann wird *expression3* zu diesem Zeigerausdruck hinzugefügt, um einen neuen Zeigerausdruck zu bilden. Dies geht so lange weiter, bis der letzte indexierte Ausdruck hinzugefügt wurde.  Der Dereferenzierungsoperator \(**\***\) wird angewendet, nachdem der letzte indexierte Ausdruck ausgewertet wird, es sei denn, der letzte Zeigerwert spricht einen Arraytyp an.  
  
 Ausdrücke mit mehreren Indizes verweisen auf Elemente aus mehrdimensionalen Arrays.  Ein mehrdimensionales Array ist ein Array, dessen Elemente Arrays sind.  Beispielsweise ist das erste Element eines dreidimensionalen Arrays ein Array mit zwei Dimensionen.  Im folgenden Beispiel wird ein einfaches, zweidimensionales Array aus Zeichen deklariert und initialisiert:  
  
```  
// expre_Subscript_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
#define MAX_ROWS 2  
#define MAX_COLS 2  
  
int main() {  
   char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };  
   for ( int i = 0; i < MAX_ROWS; i++ )  
      for ( int j = 0; j < MAX_COLS; j++ )  
         cout << c[ i ][ j ] << endl;  
}  
```  
  
## Positive und negative Indizes  
 Das erste Element eines Arrays ist Element 0.  Der Bereich eines C\+\+\-Arrays reicht von *Array*\[0\] bis *Array*\[*Größe* – 1\].  C\+\+ unterstützt jedoch die positiven und negativen Indizes.  Negative Indizes müssen innerhalb der Array\-Grenzen liegen. Andernfalls sind die Ergebnisse unvorhersehbar.  Der folgende Code zeigt positive und negative Arrayfeldindizes:  
  
```  
#include <iostream>  
using namespace std;  
  
int main() {  
    int intArray[1024];  
    for (int i = 0, j = 0; i < 1024; i++)  
    {  
        intArray[i] = j++;  
    }  
  
    cout << intArray[512] << endl;// 512  
  
    int *midArray = &intArray[512];  // pointer to the middle of the array  
  
    cout << midArray[-256] << endl;   // 256  
  
    cout << intArray[-256] << endl; // unpredictable  
}  
```  
  
 Der negative Index in der letzten Zeile erzeugt eventuell einen Laufzeitfehler, da er auf eine Adresse mit 256 Bytes weniger Arbeitsspeicher zeigt als der Ursprung des Arrays.  Der Zeiger `midArray` wird zur Mitte von `intArray` initialisiert. Daher ist es möglich, positive und negative Arrayindizes auf ihn zu verwenden.  Array\-Indexfehler generieren keine Fehler zur Kompilierzeit, führen jedoch zu unvorhersehbaren Ergebnissen.  
  
 Der Indexoperator ist kommutativ.  Daher sind die Begriffe *array*\[*index*\] und *array*\[*array*\] garantiert gleichwertig, solange der Indexoperator nicht überladen wird \(siehe [Überladene Operatoren](../cpp/operator-overloading.md)\).  Die erste Form entspricht der gängigsten Codierungspraxis, aber beide funktionieren.  
  
## Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Arrays](../cpp/arrays-cpp.md)   
 [Eindimensionale Arrays](../c-language/one-dimensional-arrays.md)   
 [Mehrdimensionale Arrays](../c-language/multidimensional-arrays-c.md)