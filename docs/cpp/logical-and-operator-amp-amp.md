---
title: 'Logischer AND-Operator: &amp; &amp; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4921a6de3072ef402ba355714ddd67328c3a3541
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406831"
---
# <a name="logical-and-operator-ampamp"></a>Logischer AND-Operator: &amp;&amp;
## <a name="syntax"></a>Syntax  
  
```  
expression && expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Der logische AND-Operator (**&&**) gibt den booleschen Wert "true" zurück, wenn beide Operanden wahr sind, und andernfalls "false" wird zurückgegeben. Die Operanden werden implizit in den Typ konvertiert **"bool"** vor der Auswertung und das Ergebnis ist vom Typ **"bool"**. Das logische AND weist eine Assoziativität von links nach rechts auf.  
  
 Die Operanden für den logischen AND-Operator müssen nicht vom gleichen Typ sein, aber sie müssen Ganzzahltypen oder Zeigertypen sein. Die Operanden sind im Allgemeinen relationale oder Gleichheitsausdrücke.  
  
 Der erste Operand wird vollständig ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die Auswertung des logischen AND-Ausdrucks fortgesetzt wird.  
  
 Der zweite Operand wird nur dann ausgewertet, wenn der erste Operand als true (ungleich Null) ausgewertet wird. Diese Auswertung eliminiert die unnötige Auswertung des zweiten Operanden, wenn der Ausdruck der logischen AND-Operation gleich FALSE ist. Mithilfe dieser Kurzschlussauswertung können Sie Dereferenzierungen durch NULL-Zeiger verhindern, wie im folgenden Beispiel gezeigt:  
  
```cpp 
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 Wenn `pch` null (0) ist, wird die rechte Seite des Ausdrucks niemals ausgewertet. Daher ist die Zuweisung durch einen NULL-Zeiger unmöglich.  
  
## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für &&  
 Die **und** -Operator ist die ausgeschriebene Variante von **&&**. Es gibt zwei Möglichkeiten, den Zugriff auf die **und** -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit der [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).  
  
## <a name="example"></a>Beispiel  
  
```cpp 
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
 [C++-Built-Operatoren, Rangfolge und Assoziativität](cpp-built-in-operators-precedence-and-associativity.md)  
 [C++-Built-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C-Operatoren (logisch)](../c-language/c-logical-operators.md)