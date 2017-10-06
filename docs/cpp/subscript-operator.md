---
title: 'Tiefgestellt-Operator: | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '[]'
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
caps.latest.revision: 9
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
ms.openlocfilehash: 21831cbd727477336c53e9d72e4bea95e123aa81
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="subscript-operator"></a>Tiefgestellt-Operator:
## <a name="syntax"></a>Syntax  
  
```  
  
postfix-expression [ expression ]  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein postfixausdruck (der auch ein primärer Ausdruck sein kann) gefolgt von dem Indexoperator **[]**, gibt eine Arrayindizierung.  
  
 Weitere Informationen zu verwalteten Arrays finden Sie unter [Arrays](../windows/arrays-cpp-component-extensions.md).  
  
 In der Regel der dargestellte Wert *postfixausdruck* ein Zeigerwert, z. B. ein Arraybezeichner, und *Ausdruck* ist ein Ganzzahlwert (einschließlich Enumerationstypen). Syntaktisch erforderlich ist allerdings nur, dass einer der Ausdrücke vom Zeigertyp und der andere Ausdruck vom Ganzzahltyp ist. Daher kann der ganzzahlige Wert der *Postfix-Expression* Position und der Zeigerwert kann in eckigen Klammern an die *Ausdruck* oder subscript Position. Betrachten Sie das folgende Codefragment:  
  
```  
int nArray[5] = { 0, 1, 2, 3, 4 };  
cout << nArray[2] << endl;            // prints "2"  
cout << 2[nArray] << endl;            // prints "2"  
```  
  
 Im vorherigen Beispiel ist der Ausdruck `nArray[2]` identisch mit dem Ausdruck `2[nArray]`. Der Grund dafür ist, die das Ergebnis eines Indexausdrucks *e1***[** *e2* **]** wird:  
  
 **\*((** *e2* **)** * + * **(***e1***))**  
  
 Die Adresse, die durch den Ausdruck ergab ist *e2* Byte der Absenderadresse *e1*. Stattdessen wird die Adresse skaliert, um das nächste Objekt im Array yield *e2*. Zum Beispiel:  
  
```  
double aDbl[2];  
```  
  
 Die Adressen der `aDb[0]` und `aDb[1]` sind 8 Bytes auseinander – die Größe eines Objekts vom Typ **doppelte**. Diese Skalierung nach Objekttyp wird von der Programmiersprache C++ automatisch ausgeführt und ist definiert [Additive Operatoren](../cpp/additive-operators-plus-and.md) , in dem Addition und Subtraktion von Operanden des Zeigertyps erläutert.  
  
 Ein indexierte Ausdruck kann auch mehrere Indizes haben, wie folgt:  
  
 *expression1* **[***expression2***] [***expression3***]**...  
  
 indexierte Ausdrücke sind von links nach rechts angeordnet. Der äußerste linke indexierte Ausdruck *expression1***[***expression2***]** wird zuerst ausgewertet. Die Adresse, die sich aus dem Hinzufügen von *expression1* und *expression2* ergibt, bildet einen Zeigerausdruck. Dann wird *expression3* zu diesem Zeigerausdruck hinzugefügt, um einen neuen Zeigerausdruck zu bilden. Dies geht so lange weiter, bis der letzte Subscriptausdruck hinzugefügt wurde. Der Dereferenzierungsoperator (**\***) wird angewendet, nachdem der letzte Indexierte Ausdruck ausgewertet wird, es sei denn, der letzte Zeigerwert einen Arraytyp spricht.  
  
 Ausdrücke mit mehreren Indizes verweisen auf Elemente aus mehrdimensionalen Arrays. Ein mehrdimensionales Array ist ein Array, dessen Elemente Arrays sind. Beispielsweise ist das erste Element eines dreidimensionalen Arrays ein Array mit zwei Dimensionen. Im folgenden Beispiel wird ein einfaches, zweidimensionales Array aus Zeichen deklariert und initialisiert:  
  
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
  
## <a name="positive-and-negative-subscripts"></a>Positive und negative Indizes  
 Das erste Element eines Arrays ist Element 0. Der Bereich eines C++-Arrays reicht von *Array*[0], *Array*[*Größe* - 1]. C++ unterstützt jedoch die positiven und negativen Indizes. Negative Indizes müssen innerhalb der Array-Grenzen liegen. Andernfalls sind die Ergebnisse unvorhersehbar. Der folgende Code zeigt positive und negative Arrayfeldindizes:  
  
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
  
 Der negative Index in der letzten Zeile erzeugt eventuell einen Laufzeitfehler, da er auf eine Adresse mit 256 Bytes weniger Arbeitsspeicher zeigt als der Ursprung des Arrays. Der Zeiger `midArray` wird zur Mitte von `intArray` initialisiert. Daher ist es möglich, positive und negative Arrayindizes auf ihn zu verwenden. Array-Indexfehler generieren keine Fehler zur Kompilierzeit, führen jedoch zu unvorhersehbaren Ergebnissen.  
  
 Der Indexoperator ist kommutativ. Daher sind die Begriffe *Array*[*Index*] und *Array*[*Array*] garantiert gleichwertig sein, solange der Feldindex Operator nicht überladen wird (siehe [überladene Operatoren](../cpp/operator-overloading.md)). Die erste Form entspricht der gängigsten Codierungspraxis, aber beide funktionieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Arrays](../cpp/arrays-cpp.md)   
 [Eindimensionale Arrays](../c-language/one-dimensional-arrays.md)   
 [Mehrdimensionale Arrays](../c-language/multidimensional-arrays-c.md)
