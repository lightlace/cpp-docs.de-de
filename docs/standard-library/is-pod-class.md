---
title: is_pod-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_pod
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 2236d6a9796b1353b919a63620606242cde169bd
ms.lasthandoff: 02/24/2017

---
# <a name="ispod-class"></a>is_pod-Klasse
Testet, ob der Typ POD ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
struct is_pod;
```  
  
#### <a name="parameters"></a>Parameter  
*T*  
Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
`is_pod<T>::value` ist `true`, wenn der Typ *T* Plain Old Data (POD) ist. Andernfalls ist der Wert `false`.  
  
Arithmetische Typen, Enumerationstypen, Zeigertypen und Zeiger auf Membertypen sind POD.  
  
Eine cv-qualifizierte Version eines POD-Typs ist selbst ein POD-Typ.  
  
Ein Array von POD ist selbst POD.  
  
Eine Struktur oder Union, all deren nicht statische Datenmember POD sind, ist selbst POD, wenn sie Folgendes aufweist:  
  
-   Keine benutzerdeklarierten Konstruktoren  
  
-   Keine privaten oder geschützten nicht statischen Datenmember  
  
-   Keine Basisklassen  
  
-   Keine virtuellen Funktionen  
  
-   Keine nicht statischen Datenmember des Verweistyps  
  
-   Keinen benutzerdefinierten Kopierzuweisungsoperator  
  
-   Keinen benutzerdefinierten Destruktor  
  
Aus diesem Grund können Sie rekursiv POD-Strukturen und -Arrays erstellen, die POD-Strukturen und -Arrays enthalten.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial {   
    int val;   
};   
  
struct throws {   
    throws() {}  // User-declared ctor, so not POD
  
    int val;   
};   
  
int main() {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
is_pod<trivial> == true  
is_pod<int> == true  
is_pod<throws> == false  
```  
  
## <a name="requirements"></a>Anforderungen  
**Header:** \<type_traits>  
  
**Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
[<type_traits>](../standard-library/type-traits.md)




