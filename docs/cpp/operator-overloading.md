---
title: "Operatoren überladen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- operator_cpp
- operator
dev_langs: C++
helpviewer_keywords:
- redefinable operators [C++]
- non-redefinable operators [C++]
- operator keyword [C++]
- operators [C++], overloading
- operator overloading
ms.assetid: 56ad4c4f-dd0c-45e0-adaa-08fe98cb1f8e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 617236d30f3c4473f6c7785db97789105d6cd565
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="operator-overloading"></a>Operatorüberladung
Das `operator`-Schlüsselwort deklariert eine Funktion, die angibt, welche Bedeutung `operator-symbol` bei der Anwendung auf Instanzen einer Klasse hat. Dadurch erhält der Operator mehrere Bedeutungen, oder er wird "überladen". Der Compiler unterscheidet zwischen verschiedenen Bedeutungen eines Operators, indem er die Typen seiner Operanden überprüft.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
type operator operator-symbol ( parameter-list )  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Funktion der meisten integrierten Operatoren global oder klassenweise neu definieren. Überladene Operatoren werden als Funktionen implementiert.  
  
 Der Name eines überladenen Operators ist `operator x`, wobei `x` ist der Operator, wie er in der folgenden Tabelle angezeigt wird. Um beispielsweise den Additionsoperator zu überladen, definieren Sie eine Funktion mit dem Namen `operator+`. Ebenso definieren Sie zum Überladen des Additionszuweisungsoperators `+=` eine Funktion mit dem Namen `operator+=`.  
  
### <a name="redefinable-operators"></a>Neu definierbare Operatoren  
  
|Operator|Name|Typ|  
|--------------|----------|----------|  
|`,`|Komma|Binär|  
|`!`|Logisches NOT|Unär|  
|`!=`|Ungleichheit|Binär|  
|`%`|Modulooperator|Binär|  
|`%=`|Modulozuweisung|Binär|  
|`&`|Bitweises AND|Binär|  
|`&`|Address-of|Unär|  
|`&&`|Logisches AND|Binär|  
|`&=`|Bitweise AND-Zuweisung|Binär|  
|`( )`|Funktionsaufruf |—|  
|`( )`|Umwandlungsoperator|Unär|  
|`*`|Multiplikation|Binär|  
|`*`|Zeiger-Dereferenzierung|Unär|  
|`*=`|Multiplikationszuweisung|Binär|  
|`+`|Addition|Binär|  
|`+`|Unäres Plus|Unär|  
|`++`|Inkrement <sup>1</sup>|Unär|  
|`+=`|Additionszuweisung|Binär|  
|`-`|Subtraktion|Binär|  
|`-`|Unäre Negation|Unär|  
|`--`|Dekrementoperatoren <sup>1</sup>|Unär|  
|`-=`|Subtraktionszuweisung|Binär|  
|`->`|Memberauswahl|Binär|  
|`->*`|Pointer-to-member-Auswahl|Binär|  
|`/`|Division|Binär|  
|`/=`|Divisionszuweisung|Binär|  
|`<`|Kleiner als|Binär|  
|`<<`|Nach links verschieben|Binär|  
|`<<=`|Linksschiebezuweisung|Binär|  
|`<=`|Kleiner oder gleich|Binär|  
|`=`|Zuweisung|Binär|  
|`==`|Gleichheit|Binär|  
|`>`|Größer als|Binär|  
|`>=`|Größer oder gleich|Binär|  
|`>>`|Nach rechts verschieben|Binär|  
|`>>=`|Rechtsschiebezuweisung|Binär|  
|`[ ]`|Arrayfeldindex|—|  
|`^`|Exklusives OR|Binär|  
|`^=`|Exklusive OR-Zuweisung|Binär|  
|`&#124;`|Bitweises inklusives OR|Binär|  
|`&#124;=`|Bitweise inklusive OR-Zuweisung|Binär|  
|`&#124;&#124;`|Logisches OR|Binär|  
|`~`|Einerkomplement|Unär|  
|`delete`|`Delete`|—|  
|`new`|`New`|—|  
|`conversion operators`|Konvertierungsoperatoren|Unär|  
  
 1 Es gibt zwei Versionen der unären erhöht und Dekrementoperatoren: Preincrement und Postincrement.  
  
 Finden Sie unter [Allgemeine Regeln für Operatorüberladung](../cpp/general-rules-for-operator-overloading.md) für Weitere Informationen. Die Einschränkungen für die verschiedenen Kategorien von überladenen Operatoren werden in den folgenden Themen beschrieben:  
  
-   [Unäre Operatoren](../cpp/overloading-unary-operators.md)  
  
-   [Binäre Operatoren](../cpp/binary-operators.md)  
  
-   [Zuweisung](../cpp/assignment.md)  
  
-   [Funktionsaufruf](../cpp/function-call-cpp.md)  
  
-   [Indizierung](../cpp/subscripting.md)  
  
-   [Klassenmemberzugriff](../cpp/member-access.md)  
  
-   [Inkrementieren und Dekrementieren](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
-   [Benutzerdefinierte Typkonvertierungen](../cpp/user-defined-type-conversions-cpp.md)  
  
 Die Operatoren, die in der folgenden Tabelle aufgeführt sind, können nicht überladen werden. Die Tabelle enthält die Präprozessorsymbole `#` und `##`.  
  
### <a name="nonredefinable-operators"></a>Nicht neu definierbare Operatoren  
  
|||  
|-|-|  
|`Operator`|`Name`|  
|`.`|Memberauswahl|  
|`.*`|Pointer-to-member-Auswahl|  
|`::`|Bereichsauflösung|  
|`? :`|Bedingt|  
|`#`|Präprozessorkonvertierung in Zeichenfolge|  
|`##`|Präprozessorverkettung|  
  
 Obwohl überladene Operatoren in der Regel vom Compiler implizit aufgerufen werden, wenn sie im Code auftreten, können sie explizit auf dieselbe Art und Weise aufgerufen werden, wie andere Member- oder Nichtmemberfunktionen aufgerufen werden:  
  
```  
Point pt;  
pt.operator+( 3 );  // Call addition operator to add 3 to pt.  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `+`-Operator überladen, um zwei komplexe Zahlen hinzuzufügen, und das Ergebnis wird zurückgegeben.  
  
```  
// operator_overloading.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Complex {  
   Complex( double r, double i ) : re(r), im(i) {}  
   Complex operator+( Complex &other );  
   void Display( ) {   cout << re << ", " << im << endl; }  
private:  
   double re, im;  
};  
  
// Operator overloaded using a member function  
Complex Complex::operator+( Complex &other ) {  
   return Complex( re + other.re, im + other.im );  
}  
  
int main() {  
   Complex a = Complex( 1.2, 3.4 );  
   Complex b = Complex( 5.6, 7.8 );  
   Complex c = Complex( 0.0, 0.0 );  
  
   c = a + b;  
   c.Display();  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
6.8, 11.2  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
1.  [Allgemeine Regeln für die Überladung von Operatoren](../cpp/general-rules-for-operator-overloading.md)  
  
2.  [Überladen von unären Operatoren](../cpp/overloading-unary-operators.md)  
  
3.  [Binäre Operatoren](../cpp/binary-operators.md)  
  
4.  [Zuweisung](../cpp/assignment.md)  
  
5.  [Funktionsaufruf](../cpp/function-call-cpp.md)  
  
6.  [Indizierung](../cpp/subscripting.md)  
  
7.  [Memberzugriff](../cpp/member-access.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)