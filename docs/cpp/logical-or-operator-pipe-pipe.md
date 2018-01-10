---
title: 'Logischer OR -Operator: || | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '||'
dev_langs: C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a826b23f94c4eae4a4fdb5379563b015f05dde71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="logical-or-operator-"></a>Logischer OR-Operator: ||
## <a name="syntax"></a>Syntax  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Der logische OR-Operator (`||`) gibt den booleschen Wert **"true"** ist einer oder beide Operanden **"true"** und gibt **"false"** andernfalls. Die Operanden werden vor der Auswertung implizit in den Typ `bool` konvertiert. Das Ergebnis ist ein `bool`-Typ. Das logische OR weist eine Assoziativität von links nach rechts auf.  
  
 Die Operanden für den logischen OR-Operator müssen nicht vom gleichen Typ sein, aber sie müssen Ganzzahltypen oder Zeigertypen sein. Die Operanden sind im Allgemeinen relationale oder Gleichheitsausdrücke.  
  
 Der erste Operand wird vollständig ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die Auswertung des logischen OR-Ausdrucks fortgesetzt wird.  
  
 Der zweite Operand wird nur ausgewertet, wenn der erste Operand als false (0) ausgewertet wird. Diese Auswertung eliminiert die unnötige Auswertung des zweiten Operanden, wenn der logische OR-Ausdruck TRUE ist.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 Im Beispiel oben, wenn `x` entweder gleich `w`, `y` oder `z` ist, wird das zweite Argument für die `printf`-Funktion mit "true" ausgewertet, und der Wert 1 wird ausgegeben. Andernfalls wird dies mit "false" ausgewertet, und der Wert 0 (null) wird ausgegeben. Sobald eine der Bedingungen mit dem Ergebnis "true" ausgewertet wird, wird die Auswertung beendet.  
  
## <a name="operator-keyword-for-124124"></a>Operator-Schlüsselwort für &#124; &#124;  
 Die **oder** Operator ist die textentsprechung von `||`. Es gibt zwei Möglichkeiten, den Zugriff auf die **oder** -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der ["/ Za"](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
[Integrierte C++-Operatoren, Rangfolge und Assoziativität](cpp-built-in-operators-precedence-and-associativity.md) [integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Operatoren (logisch)](../c-language/c-logical-operators.md)