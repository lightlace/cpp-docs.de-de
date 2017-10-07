---
title: Indizierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], overloaded
- arrays [C++], subscripting
- subscripting [C++]
- operators [C++], overloading
- operator overloading [C++], examples
- subscript operator
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 82feaa68724e36c7ac7e739397d8a11a18e970a0
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="subscripting"></a>Indizierung 
Der Indexoperator (**[]**) wie der Funktionsaufrufoperator als binärer Operator betrachtet wird. Der Indexoperator muss eine nicht statische Memberfunktion sein, die ein einzelnes Argument akzeptiert. Dieses Argument kann einen beliebigen Typ aufweisen und legt den gewünschten Arrayindex fest.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie ein Vektor vom Typ `int` erstellt werden kann, der die Überprüfung der Begrenzungen implementiert:  
  
```  
// subscripting.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class IntVector {  
public:  
   IntVector( int cElements );  
   ~IntVector() { delete [] _iElements; }  
   int& operator[](int nSubscript);  
private:  
   int *_iElements;  
   int _iUpperBound;  
};  
  
// Construct an IntVector.  
IntVector::IntVector( int cElements ) {  
   _iElements = new int[cElements];  
   _iUpperBound = cElements;  
}  
  
// Subscript operator for IntVector.  
int& IntVector::operator[](int nSubscript) {  
   static int iErr = -1;  
  
   if( nSubscript >= 0 && nSubscript < _iUpperBound )  
      return _iElements[nSubscript];  
   else {  
      clog << "Array bounds violation." << endl;  
      return iErr;  
   }  
}  
  
// Test the IntVector class.  
int main() {  
   IntVector v( 10 );  
   int i;  
  
   for( i = 0; i <= 10; ++i )  
      v[i] = i;  
  
   v[3] = v[9];  
  
   for ( i = 0; i <= 10; ++i )  
      cout << "Element: [" << i << "] = " << v[i] << endl;  
}  
```  
  
```Output  
Array bounds violation.  
Element: [0] = 0  
Element: [1] = 1  
Element: [2] = 2  
Element: [3] = 9  
Element: [4] = 4  
Element: [5] = 5  
Element: [6] = 6  
Element: [7] = 7  
Element: [8] = 8  
Element: [9] = 9  
Array bounds violation.  
Element: [10] = 10  
```  
  
## <a name="comments"></a>Kommentare  
 Wenn `i` im vorangehenden Programm 10 erreicht, erkennt `operator[]`, dass ein Index außerhalb des gültigen Bereichs verwendet wird, und gibt eine Fehlermeldung aus.  
  
 Beachten Sie, dass die Funktion `operator[]` einen Verweistyp zurückgibt. Dadurch wird sie zu einem L-Wert, und Sie können auf beiden Seiten von Zuweisungsoperatoren indizierte Ausdrücke verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorüberladung](../cpp/operator-overloading.md)
