---
title: "Inkrementierungs-und Dekrementierungsoperatoren in Präfixnotation: ++ und--| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- C++
helpviewer_keywords:
- increment operators, syntax
- ++ operator, prefix increment operators
- operators [C++], decrement
- -- operator, prefix decrement operators
- operators [C++], increment
- decrement operators, syntax
- decrement operators
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
caps.latest.revision: 8
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
ms.openlocfilehash: 22844a2bca61b81dc5cf7c2fc4fffa45a2783078
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="prefix-increment-and-decrement-operators--and---"></a>Inkrementierungs- und Dekrementierungsoperatoren in Präfixnotation: ++ und --
## <a name="syntax"></a>Syntax  
  
```  
++ unary-expression  
-- unary-expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Präfixdekrementoperator (`++`) fügt einen Wert zu seinem Operanden hinzu. Das Ergebnis des Ausdrucks ist dieser inkrementierte Wert. Der Operand muss ein l-Wert nicht vom Typ **const**. Das Ergebnis ist ein L-Wert des gleichen Typs wie der Operand.  
  
 Der präfixdekrementoperator (**--**) entspricht dem präfixinkrementoperator mit dem Unterschied, dass der Operand um eins verringert wird und das Ergebnis dieser dekrementierte Wert ist.  

 **Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): der Operand eines Inkrement- oder Dekrement-Operators möglicherweise nicht vom Typ `bool`.
  
 Sowohl Präfix- als auch Postfixinkrement und Dekrementoperatoren beeinflussen ihre Operanden. Der wesentliche Unterschied zwischen ihnen besteht in der Reihenfolge von Inkrement und Dekrement bei der Auswertung eines Ausdrucks. (Weitere Informationen finden Sie unter [Postfix-Inkrementoperatoren und Dekrementoperatoren](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md).) In der Präfix-Form findet das Inkrement oder Dekrement statt, bevor der Wert in der Ausdrucksauswertung verwendet wird, daher ist der Wert des Ausdrucks ungleich dem Wert des Operanden. In der Postfix-Form findet das Inkrement oder Dekrement statt, nachdem der Wert in der Ausdrucksauswertung verwendet wird, daher ist der Wert des Ausdrucks der gleiche wie der Wert des Operanden. Zum Beispiel gibt das folgende Programm "`++i = 6`" aus:  
  
```  
// expre_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int i = 5;  
   cout << "++i = " << ++i << endl;  
}  
```  
  
 Ein Operand vom Typ "Ganzzahl" oder "Gleitkomma" wird durch den ganzzahligen Wert 1 inkrementiert oder dekrementiert. Der Ergebnistyp entspricht dem Operandentyp. Ein Operand vom Zeigertyp wird um die Größe des von ihm adressierten Objekts inkrementiert oder dekrementiert. Ein inkrementierter Zeiger verweist auf das nächste Objekt. Ein dekrementierter Zeiger verweist auf das vorherige Objekt.  
  
 Da Inkrement-und Dekrementoperatoren Nebeneffekte haben, verwenden von Ausdrücken mit Inkrement- oder Dekrement-Operatoren in einem [Präprozessormakro](../preprocessor/macros-c-cpp.md) können unerwünschte Ergebnisse haben. Betrachten Sie das folgende Beispiel:  
  
```  
// expre_Increment_and_Decrement_Operators2.cpp  
#define max(a,b) ((a)<(b))?(b):(a)  
  
int main()  
{  
   int i = 0, j = 0, k;  
   k = max( ++i, j );  
}  
```  
  
 Das Makro wird wie folgt erweitert:  
  
```  
k = ((++i)<(j))?(j):(++i);  
```  
  
 Wenn `i` größer oder gleich `j` oder um 1 kleiner als `j` ist, wird es zweimal inkrementiert.  
  
> [!NOTE]
>  C++-Inlinefunktionen sind in vielen Fällen Makros vorzuziehen, da diese Nebeneffekte, wie die hier beschriebenen, ausschließen und der Programmiersprache die weitere Ausführung vollständigerer Typüberprüfung ermöglichen.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Inkrementierungs- und Dekrementierungsoperatoren in Präfixnotation](../c-language/prefix-increment-and-decrement-operators.md)
