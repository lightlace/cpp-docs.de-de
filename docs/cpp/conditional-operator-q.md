---
title: 'Bedingter Operator:? : | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '?:'
- '?'
dev_langs:
- C++
helpviewer_keywords:
- conditional operators
- '? : operator'
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
caps.latest.revision: 10
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
ms.openlocfilehash: f66e1eb9364503988178c70f3628b44fa3d5b93a
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="conditional-operator--"></a>Bedingter Operator:? :
## <a name="syntax"></a>Syntax  
  
```  
  
expression ? expression : expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Der bedingte Operator (**?:**) ist ein dreifacher Operator (er übernimmt drei Operanden). Der bedingte Operator funktioniert wie folgt:  
  
-   Der erste Operand wird implizit in `bool` konvertiert. Er wird ausgewertet, und alle Nebeneffekte werden vor dem nächsten Schritt abgeschlossen.  
  
-   Wenn der erste Operand als **"true"** (1), der zweite Operand ausgewertet.  
  
-   Wenn der erste Operand als **"false"** (0), der dritte Operand ausgewertet wird.  
  
 Das Ergebnis des bedingten Operators ist das Ergebnis des ausgewerteten Operanden – der zweite oder dritte. Nur einer der letzten zwei Operanden wird in einem bedingten Ausdruck ausgewertet.  
  
 Bedingte Ausdrücke besitzen Assoziativität von rechts nach links. Der erste Operand muss ein ganzzahliger Typ oder ein Zeigertyp sein. Die folgenden Regeln gelten für die zweiten und dritten Operanden:  
  
-   Wenn beide Operanden vom selben Typ sind, ist das Ergebnis von diesem Typ.  
  
-   Wenn beide Operanden arithmetische oder Enumerationstypen Typen, die üblichen arithmetischen Konvertierungen (finden Sie im [Standardkonvertierungen](standard-conversions.md)) werden ausgeführt, um sie in einen gemeinsamen Typ zu konvertieren.  
  
-   Wenn beide Operanden Zeigertypen sind, oder wenn einer ein Zeigertyp und der andere ein konstanter Ausdruck ist, der 0 ergibt, werden Zeigerkonvertierungen ausgeführt, um sie in einen gemeinsamen Typ zu konvertieren.  
  
-   Wenn beide Operanden Verweistypen sind, werden Verweiskonvertierungen ausgeführt, um sie in einen gemeinsamen Typ zu konvertieren.  
  
-   Wenn beide Operanden vom Typ "void" sind, ist der gemeinsame Typ "void".  
  
-   Wenn beide Operanden vom selben benutzerdefinierten Typ sind, ist der gemeinsame Typ dieser Typ.  
  
-   Wenn die Operanden unterschiedliche Typen aufweisen und mindestens einer der Operanden den benutzerdefinierten Typ aufweist, werden die Sprachregeln zum Bestimmen des allgemeinen Typs verwendet. (Siehe obige Warnung.)  
  
 Alle Kombinationen von zweiten und dritten Operanden, die nicht in der vorangehenden Liste enthalten sind, sind ungültig. Der Ergebnistyp ist der gemeinsame Typ, und es ist ein l-Wert, wenn die zweiten und dritten Operanden vom selben Typ und beide l-Werte sind.  
  
> [!WARNING]
>  Wenn die Typen der zweiten und dritten Operanden nicht identisch sind, werden komplexe Typkonvertierungsregeln gemäß C++-Standard aufgerufen. Diese Konvertierungen können zu unerwartetem Verhalten führen, einschließlich der Erstellung und Zerstörung von temporären Objekten. Aus diesem Grund empfehlen wir dringend, dass Sie entweder (1) keine benutzerdefinierten Typen als Operanden mit dem bedingten Operator verwenden oder (2) explizit jeden Operanden in einen gemeinsamen Typ umwandeln, wenn Sie benutzerdefinierte Typen verwenden.  
  
## <a name="example"></a>Beispiel  
  
```  
// expre_Expressions_with_the_Conditional_Operator.cpp  
// compile with: /EHsc  
// Demonstrate conditional operator  
#include <iostream>  
using namespace std;  
int main() {  
   int i = 1, j = 2;  
   cout << ( i > j ? i : j ) << " is greater." << endl;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Bedingter Ausdrucksoperator](../c-language/conditional-expression-operator.md)
