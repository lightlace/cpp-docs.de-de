---
title: Relationale C-Operatoren C-Gleichheitsoperatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- relational operators, syntax
- equality operator
- operators [C], equality
- equality operator, syntax
- operators [C], relational
ms.assetid: c89a3815-a65e-4e0d-8333-0e8dc7fdb30b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b1581fe5a952d1ea8e78f29e606af5ac148f3b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="c-relational-and-equality-operators"></a>C-Operatoren (relational) und C-Gleichheitsoperatoren
Die binären Gleichheits- und relationalen Operatoren vergleichen ihren ersten Operanden mit ihrem zweiten Operanden, um die Gültigkeit der angegebenen Beziehung zu testen. Das Ergebnis eines relationalen Ausdrucks beträgt 1, wenn die getestete Beziehung "true" ist, und er beträgt 0, wenn sie "false" ist. Das Ergebnis hat den Typ `int`.  
  
 **Syntax**  
  
 *relational-expression*:  
 *shift-expression*  
  
 *relational-expression*  **\<**  *shift-expression*  
  
 *relational-expression*  **>**  *shift-expression*  
  
 *relational-expression*  **\<=**  *shift-expression*  
  
 *relational-expression*  **>=**  *shift-expression*  
  
 *equality-expression*:  
 *relational-expression*  
  
 *equality-expression*  **==**  *relational-expression*  
  
 *equality-expression*  **!=**  *relational-expression*  
  
 Mit den Gleichheits- und relationalen Operatoren werden die folgenden Beziehungen getestet:  
  
|Operator|Getestete Beziehung|  
|--------------|-------------------------|  
|**\<**|Erster Operand kleiner als zweiter Operand|  
|**>**|Erster Operand größer als zweiter Operand|  
|**\<=**|Erster Operand kleiner als oder gleich dem zweiten Operand|  
|**>=**|Erster Operand größer als oder gleich dem zweiten Operand|  
|`==`|Erster Operand gleich dem zweiten Operand|  
|`!=`|Erster Operand ungleich dem zweiten Operand|  
  
 Die ersten vier Operatoren in der obigen Auflistung haben Priorität gegenüber den Gleichheitsoperatoren (`==` und `!=`). Weitere Informationen zu den Prioritäten erhalten Sie in der Tabelle für [Rangfolge und Assoziativität von C-Operatoren](../c-language/precedence-and-order-of-evaluation.md).  
  
 Die Operanden können einen Ganzzahl-, Gleitkomma- oder Zeigertyp haben. Die Typen der Operanden können sich unterscheiden. Relationale Operatoren führen die üblichen arithmetischen Konvertierungen für Operanden des Ganzzahl- und Gleitkommatyps aus. Außerdem können Sie die folgenden Kombinationen von Operandentypen mit den Gleichheits- und relationalen Operatoren verwenden:  
  
-   Beide Operanden des jeweiligen Gleichheits- oder relationalen Operators können Zeiger auf den gleichen Typ sein. Für den Gleichheitsoperator (`==`) und den Ungleichheitsoperator (`!=`) gibt das Ergebnis des Vergleichs an, ob die zwei Zeiger denselben Speicherbereich adressieren. Für die anderen relationalen Operatoren (**\<**, **>**, **\<**= und **>**=) gibt das Ergebnis des Vergleichs die relative Position der zwei Speicheradressen der Objekte an, auf die gezeigt wird. Mit relationalen Operatoren werden nur Offsets verglichen.  
  
     Der Zeigervergleich wird nur für Teile des gleichen Objekts definiert. Wenn die Zeiger auf Member eines Arrays verweisen, ist der Vergleich identisch mit dem Vergleich der entsprechenden tiefgestellten Zeichen. Die Adresse des ersten Arrayelements ist "kleiner als" die Adresse des letzten Elements. Im Fall von Strukturen sind Zeiger auf später deklarierte Strukturmember Größer-als-Zeiger auf Member, die früher in der Struktur deklariert werden. Zeiger auf die Member derselben Union sind gleich.  
  
-   Ein Zeigerwert kann mit dem konstanten Wert 0 auf Gleichheit (`==`) oder Ungleichheit (`!=`) geprüft werden. Ein Zeiger mit einem Wert von 0 wird als NULL-Zeiger bezeichnet, d. h. er zeigt nicht auf einen gültigen Speicherbereich.  
  
-   Die Gleichheitsoperatoren befolgen die gleichen Regeln wie relationale Operatoren, aber sie lassen zusätzliche Möglichkeiten zu: Ein Zeiger kann mit einem konstanten Integralausdruck mit dem Wert 0 oder mit einem Zeiger auf `void` verglichen werden. Wenn beide Zeiger NULL-Zeiger sind, sind sie gleichwertig. Mit Gleichheitsoperatoren werden Segmente und Offsets verglichen.  
  
## <a name="examples"></a>Beispiele  
 In den unten gezeigten Beispielen werden Gleichheits- und relationale Operatoren veranschaulicht.  
  
```  
int x = 0, y = 0;  
if ( x < y )  
```  
  
 Da `x` und `y` gleich sind, ergibt der Ausdruck in diesem Beispiel den Wert 0.  
  
```  
char array[10];  
char *p;  
  
for ( p = array; p < &array[10]; p++ )  
    *p = '\0';  
```  
  
 Das Fragment in diesem Beispiel legt jedes Element von `array` als Nullzeichenkonstante fest.  
  
```  
enum color { red, white, green } col;  
   .  
   .  
   .  
   if ( col == red )  
   .  
   .  
   .  
```  
  
 Diese Anweisungen deklarieren die Enumerationsvariable `col` mit dem `color`-Tag. Die Variable kann jederzeit einen Ganzzahlwert von 0, 1 oder 2 enthalten, der eines der Elemente des Enumerationssatzes `color` darstellt: die Farbe Rot, Weiß oder Grün. Wenn `col` den Wert 0 bei Ausführung der **if**-Anweisung enthält, werden alle von **if** abhängigen Anweisungen ausgeführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Relationale Operatoren: \<, >, \<= und >=](../cpp/relational-operators-equal-and-equal.md)   
 [Gleichheitsoperatoren: == und !=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)