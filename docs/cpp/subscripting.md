---
title: 'Indizierung '
ms.date: 11/04/2016
helpviewer_keywords:
- subscript operator [C++], overloaded
- arrays [C++], subscripting
- subscripting [C++]
- operators [C++], overloading
- operator overloading [C++], examples
- subscript operator
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
ms.openlocfilehash: 376cacc3f70995c271a29b741ad266049da45785
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330549"
---
# <a name="subscripting"></a>Indizierung 

Der Indexoperator (**[]**), wie der Funktionsaufrufoperator wird als binärer Operator betrachtet. Der Indexoperator muss eine nicht statische Memberfunktion sein, die ein einzelnes Argument akzeptiert. Dieses Argument kann einen beliebigen Typ aufweisen und legt den gewünschten Arrayindex fest.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie einen Vektor vom Typ erstellen **Int** , die Überprüfung der Begrenzungen implementiert:

```cpp
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

Wenn `i` in der vorangehenden Programm 10 erreicht **[]-Operator** erkennt, dass ein Index außerhalb des gültigen Bereichs verwendet wird und eine Fehlermeldung ausgegeben.

Beachten Sie, dass die Funktion **[]-Operator** einen Verweistyp zurückgibt. Dadurch wird sie zu einem L-Wert, und Sie können auf beiden Seiten von Zuweisungsoperatoren indizierte Ausdrücke verwenden.

## <a name="see-also"></a>Siehe auch

[Operatorüberladung](../cpp/operator-overloading.md)