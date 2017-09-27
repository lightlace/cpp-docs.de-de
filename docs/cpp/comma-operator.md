---
title: Kommaoperator:, | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '%2C'
- ','
dev_langs:
- C++
helpviewer_keywords:
- comma operator
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
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
ms.openlocfilehash: e5e7af401a0c435931f6952674d97752d2ac7730
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comma-operator-"></a>Kommaoperator: ,
Ermöglicht das Gruppieren von zwei Anweisungen, wo eine erwartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
expression , expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Operator Komma weist eine Assoziativität von links nach rechts auf. Zwei Ausdrücke, die durch ein Komma getrennt werden, werden von links nach rechts ausgewertet. Der linke Operand wird immer ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor der rechte Operand ausgewertet wird.  
  
 Kommas können in einigen Kontexten, z. B. Funktionsargumentlisten, als Trennzeichen verwendet werden. Verwechseln Sie die Verwendung des Kommas als Trennzeichen nicht mit seiner Verwendung als Operator. Die beiden Anwendungsmöglichkeiten sind vollkommen unterschiedlich.  
  
 Betrachten Sie den Ausdruck  
  
 *E1* , *e2*  
  
 Dem Typ und Wert des Ausdrucks entsprechen Typ und Wert der *e2*; das Ergebnis der Auswertung *e1* wird verworfen. Dieses Ergebnis ist ein L-Wert, wenn der rechte Operand ein L-Wert ist.  
  
 Während das Komma normalerweise als Trennzeichen verwendet wird (z. B. in tatsächlichen Argumenten für Funktionen oder Aggregatinitialisierer), müssen der Komma-Operator und seine Operanden in Klammern eingeschlossen werden. Zum Beispiel:  
  
```  
func_one( x, y + 2, z );  
func_two( (x--, y + 2), z );  
```  
  
 Im obigen Funktionsaufruf an `func_one` werden drei durch Trennzeichen getrennte Argumente übergeben: `x`, `y + 2` und `z`. Im Funktionsaufruf an `func_two` zwingen Klammern den Compiler, das erste Komma als Operator für sequenzielle Auswertung zu interpretieren. Dieser Funktionsaufruf übergibt zwei Argumente an `func_two`. Das erste Argument ist das Ergebnis der Sequentialauswertungsoperation `(x--, y + 2)`, welche den Wert und den Typ des Ausdrucks `y + 2` hat; das zweite Argument ist `z`.  
  
## <a name="example"></a>Beispiel  
  
```  
// cpp_comma_operator.cpp  
#include <stdio.h>  
int main () {  
   int i = 10, b = 20, c= 30;  
   i = b, c;  
   printf("%i\n", i);  
  
   i = (b, c);  
   printf("%i\n", i);  
}  
```  
  
```Output  
20  
30  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Operator für sequenzielle Auswertungen](../c-language/sequential-evaluation-operator.md)
