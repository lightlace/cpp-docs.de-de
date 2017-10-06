---
title: Const_cast-Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
caps.latest.revision: 7
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
ms.openlocfilehash: 8f72367cb4970b2ce0121efc43b79691155808df
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="constcast-operator"></a>const_cast-Operator
Entfernt die **const**, `volatile`, und **__unaligned** -Attribute aus einer Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Zeiger auf einen beliebigen Objekttyp oder ein Zeiger auf einen Datenmember explizit in einen Typ, der identisch ist konvertiert werden kann die **const**, `volatile`, und **__unaligned** Qualifizierer. Für Zeiger und Verweise verweist das Ergebnis auf das ursprüngliche Objekt. Für Zeiger auf Datenmember, verweist das Ergebnis auf denselben Member wie der ursprüngliche (uncast) Zeiger auf Datenmember. Je nach Typ des verweisenden Objekts, führt ein Schreibvorgang durch den resultierenden Zeiger, Verweis oder Zeiger auf Datenmember möglicherweise zu nicht definiertem Verhalten.  
  
 Sie können den Operator `const_cast` nicht verwenden, um den konstanten Status einer konstanten Variable direkt zu überschreiben.  
  
 Der `const_cast`-Operator konvertiert einen NULL-Zeigerwert in den NULL-Zeigerwert des Zieltyps.  
  
## <a name="example"></a>Beispiel  
  
```  
// expre_const_cast_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CCTest {  
public:  
   void setNumber( int );  
   void printNumber() const;  
private:  
   int number;  
};  
  
void CCTest::setNumber( int num ) { number = num; }  
  
void CCTest::printNumber() const {  
   cout << "\nBefore: " << number;  
   const_cast< CCTest * >( this )->number--;  
   cout << "\nAfter: " << number;  
}  
  
int main() {  
   CCTest X;  
   X.setNumber( 8 );  
   X.printNumber();  
}  
```  
  
 In der Zeile, die `const_cast` enthält, lautet der Datentyp des `this` Zeigers `const CCTest *`. Der Operator `const_cast` ändert den Datentyp des `this`-Zeigers in `CCTest *` und ermöglicht die Änderung des Members `number`. Die Umwandlung erfolgt nur für den Rest der Anweisung, in der er angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlungsoperatoren](../cpp/casting-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
