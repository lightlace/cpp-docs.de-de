---
title: "checked_array_iterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/checked_array_iterator"
  - "checked_array_iterator"
  - "std::checked_array_iterator"
  - "std.checked_array_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "checked_array_iterator"
  - "checked_array_iterator-Klasse"
  - "checked_array_iterator, Syntax"
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# checked_array_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `checked_array_iterator`\-Klasse ermöglicht es Ihnen, ein Array oder einen Zeiger in einen überprüfter Iterator zu transformieren.  Verwenden Sie diese Klasse \(mithilfe der [make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md)\-Funktion\) als Wrapper für unformatierte Zeiger oder Arrays als entsprechende Methode zum Bereitstellen von Überprüfungen und zum Verwalten nicht aktivierter Zeigerwarnungen, anstatt diese Warnungen global zu deaktivieren.  Bei Bedarf können Sie die deaktivierte Version dieser [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md)\-Klasse verwenden.  
  
> [!NOTE]
>  Bei dieser Klasse handelt es sich um eine Microsoft\-Erweiterung der C\+\+\-Standardbibliothek.  Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C\+\+\-Standardbuildumgebungen übertragbar, die die Microsoft\-Erweiterung nicht unterstützen.  Ein Beispiel, in dem das Schreiben von Code veranschaulicht wird, bei dem die Verwendung dieser Klasse nicht erforderlich ist, finden Sie im zweiten Beispiel weiter unten.  
  
## Syntax  
  
```  
template <class _Iterator>  
    class checked_array_iterator;  
```  
  
## Hinweise  
 Diese Klasse wird im [stdext](../standard-library/stdext-namespace.md)\-Namespace definiert.  
  
 Weitere Informationen und Beispielcode zu überprüften Iteratoren finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
## Beispiel  
 Im folgenden Beispiel wird das Definieren und Verwenden eines überprüften Arrayiterators veranschaulicht.  
  
 Wenn die Größe des Ziel nicht ausreicht, um alle kopierten Elemente zu halten, wie es bei Änderung der folgenden Zeile der Fall wäre:  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
```  
  
 bis  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));  
```  
  
 Ein Laufzeitfehler tritt auf.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
```  
  
  **\( 0 1 2 3 4 \)**  
**\( 0 1 2 3 4 \)**   
## Beispiel  
 Um die Notwendigkeit für die `checked_array_iterator`\-Klasse bei Verwendung von C\+\+\-Standardbibliotheks\-Algorithmen zu vermeiden, berücksichtigen Sie die Verwendung von `vector` anstelle eines dynamisch zugeordneten Arrays.  Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**   
### Konstruktoren  
  
|||  
|-|-|  
|[checked\_array\_iterator](../Topic/checked_array_iterator::checked_array_iterator.md)|Erstellt aus einem zugrunde liegenden Iterator einen standardmäßigen `checked_array_iterator` oder `checked_array_iterator`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[difference\_type](../Topic/checked_array_iterator::difference_type.md)|Ein Typ, mit dem der Unterschied zwischen zwei `checked_array_iterator`en bereitgestellt wird, die auf Elemente innerhalb desselben Containers verweisen.|  
|[pointer](../Topic/checked_array_iterator::pointer.md)|Ein Typ, mit dem ein Zeiger auf ein Element bereitgestellt wird, die von `checked_array_iterator` adressiert werden.|  
|[Verweis](../Topic/checked_array_iterator::reference.md)|Ein Typ, mit dem ein Verweis auf ein Element bereitgestellt wird, die von `checked_array_iterator` adressiert werden.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Basis](../Topic/checked_array_iterator::base.md)|Stellt den zugrunde liegenden Iterator aus `checked_array_iterator` wieder her.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\=\=](../Topic/checked_array_iterator::operator==.md)|Prüft zwei `checked_array_iterator`en auf Gleichheit.|  
|[Operator\!\=](../Topic/checked_array_iterator::operator!=.md)|Prüft zwei `checked_array_iterator`en auf Ungleichheit.|  
|[Operator \<](../Topic/checked_array_iterator::operator%3C.md)|Testet, ob `checked_array_iterator` links vom Operator kleiner als `checked_array_iterator` auf der rechten Seite ist.|  
|[Operator \>](../Topic/checked_array_iterator::operator%3E.md)|Testet, ob `checked_array_iterator` links vom Operator größer als `checked_array_iterator` auf der rechten Seite ist.|  
|[Operator \<\=](../Topic/checked_array_iterator::operator%3C=.md)|Testet, ob `checked_array_iterator` links vom Operator kleiner oder gleich `checked_array_iterator` auf der rechten Seite ist.|  
|[Operator \>\=](../Topic/checked_array_iterator::operator%3E=.md)|Testet, ob `checked_array_iterator` links vom Operator größer oder gleich `checked_array_iterator` auf der rechten Seite ist.|  
|[operator\*](../Topic/checked_array_iterator::operator*.md)|Gibt das Element zurück, das ein `checked_array_iterator` adressiert.|  
|[operator\-\>](../Topic/checked_array_iterator::operator-%3E.md)|Gibt einen Zeiger auf das Element zurück, das von `checked_array_iterator` adressiert wird.|  
|[operator\+\+](../Topic/checked_array_iterator::operator++.md)|Erhöht `checked_array_iterator` zum nächsten Element.|  
|[Operator\-\-](../Topic/checked_array_iterator::operator--.md)|Verringert `checked_array_iterator` zum vorherigen Element.|  
|[operator \+\=](../Topic/checked_array_iterator::operator+=.md)|Fügt `checked_array_iterator` einem angegebenen Offset hinzu.|  
|[operator\+](../Topic/checked_array_iterator::operator+.md)|Fügt einen Offset zu einem Iterator hinzu und gibt den neuen `checked_array_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.|  
|[Operator\-\=](../Topic/checked_array_iterator::operator-=.md)|Verringert einen angegebenen Offset von `checked_array_iterator`.|  
|[operator\-](../Topic/checked_array_iterator::operator-.md)|Verringert einen Offset von einem Iterator und gibt den neuen `checked_array_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.|  
|[operator&#91;&#93;](../Topic/checked_array_iterator::operator.md)|Gibt einen Verweis auf ein Elementoffset aus dem Element zurück, das von `checked_array_iterator` mithilfe der angegebenen Anzahl von Positionen adressiert wird.|  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Standard Template Library](../misc/standard-template-library.md)