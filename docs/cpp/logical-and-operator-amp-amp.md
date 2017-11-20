---
title: 'Logischer AND-Operator: &amp; &amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&&'
dev_langs:
- C++
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5a594efcc987fba69ceb17e7e09d10470adab75f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="logical-and-operator-ampamp"></a>Logischer AND-Operator:&amp;&amp;
## <a name="syntax"></a>Syntax  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Der logische AND-Operator (**&&**) gibt den booleschen Wert **"true"** Wenn beide Operanden **"true"** und gibt **"false"** andernfalls. Die Operanden werden vor der Auswertung implizit in den Typ `bool` konvertiert. Das Ergebnis ist ein `bool`-Typ. Das logische AND weist eine Assoziativität von links nach rechts auf.  
  
 Die Operanden für den logischen AND-Operator müssen nicht vom gleichen Typ sein, aber sie müssen Ganzzahltypen oder Zeigertypen sein. Die Operanden sind im Allgemeinen relationale oder Gleichheitsausdrücke.  
  
 Der erste Operand wird vollständig ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die Auswertung des logischen AND-Ausdrucks fortgesetzt wird.  
  
 Der zweite Operand wird nur dann ausgewertet, wenn der erste Operand als true (ungleich Null) ausgewertet wird. Diese Auswertung eliminiert die unnötige Auswertung des zweiten Operanden, wenn der Ausdruck der logischen AND-Operation gleich false ist. Mithilfe dieser Kurzschlussauswertung können Sie Dereferenzierungen durch NULL-Zeiger verhindern, wie im folgenden Beispiel gezeigt:  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 Wenn `pch` null (0) ist, wird die rechte Seite des Ausdrucks niemals ausgewertet. Daher ist die Zuweisung durch einen NULL-Zeiger unmöglich.  
  
## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für &&  
 Die **und** Operator ist die textentsprechung von ** && **. Es gibt zwei Möglichkeiten, den Zugriff auf die **und** -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](cpp-built-in-operators-precedence-and-associativity.md) [integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Operatoren (logisch)](../c-language/c-logical-operators.md)