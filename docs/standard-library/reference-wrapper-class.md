---
title: reference_wrapper-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reference_wrapper
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
- functional/std::reference_wrapper::result_type
- functional/std::reference_wrapper::type
- functional/std::reference_wrapper::get
- functional/std::reference_wrapper::operator()
dev_langs:
- C++
helpviewer_keywords:
- reference_wrapper class
- reference_wrapper
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: 21
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 57485779c1813a0537829a940047d688907a82a7
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="referencewrapper-class"></a>reference_wrapper-Klasse
Umschließt einen Verweis.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
class reference_wrapper  
{  
public:  
    typedef Ty type;  
 
    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types> 
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
 
private:  
    Ty *ptr; // exposition only  
};  
```  
  
## <a name="remarks"></a>Hinweise  
Ein `reference_wrapper<Ty>`-Wrapper kann um einen Verweis auf ein Objekt oder eine Funktion des Typs `Ty` über eine Kopie erstellt und zugewiesen werden und enthält einen Zeiger, der auf ein Objekt dieses Typs zeigt. Ein `reference_wrapper` kann zum Speichern von Verweisen in Standardcontainern und zum Übergeben von Objekten durch einen Verweis auf `std::bind` verwendet werden.  
  
Der `Ty`-Typ muss ein Objekttyp oder Funktionstyp sein, oder eine statische Assertion kann nicht zum Zeitpunkt der Kompilierung ausgeführt werden.  
  
Die Hilfsfunktionen [std::ref](functional-functions.md#ref) und [std::cref](functional-functions.md#cref) dienen zum Erstellen von `reference_wrapper`-Objekten.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[reference_wrapper](#reference_wrapper)|Erstellt ein Objekt vom Typ `reference_wrapper`.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[RESULT_TYPE](#result_type)|Der schwache Ergebnistyp des umschlossenen Verweises.|  
|[Datentyp](#type)|Der Typ des umschlossenen Verweises.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[get](#get)|Ruft den umschlossenen Verweis ab.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[reference_wrapper::operator Ty&amp;](#op_ty_amp)|Ruft einen Zeiger auf den umschlossenen Verweis ab.|  
|[reference_wrapper::operator()](#op_call)|Ruft den umschlossenen Verweis auf.|  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
##  <a name="get"></a> reference_wrapper::get  
 Ruft den umschlossenen Verweis ab.  
  
```  
Ty& get() const noexcept;
```  
  
### <a name="remarks"></a>Hinweise  
Die Memberfunktion gibt den umschlossenen Verweis zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__reference_wrapper_get.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="op_ty_amp"></a> reference_wrapper::operator Ty&amp;  
 Ruft den umschlossenen Verweis auf.  
  
```  
operator Ty&() const noexcept;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `*ptr`zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__reference_wrapper_operator_cast.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "(int)rwi = " << (int)rwi << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
(int)rwi = 1  
```  
  
##  <a name="op_call"></a> reference_wrapper::operator()  
 Ruft den umschlossenen Verweis auf.  
  
```  
template <class... Types>  
auto operator()(Types&&... args);
```  
  
### <a name="parameters"></a>Parameter  
 `Types`  
 Die Argumentlisttypen.  
  
 `args`  
 Die Argumentliste.  
  
### <a name="remarks"></a>Hinweise  
 Das Vorlagenmember `operator()` gibt `std::invoke(get(), std::forward<Types>(args)...)` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__reference_wrapper_operator_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    std::reference_wrapper<int (int)> rwi(neg);   
  
    std::cout << "rwi(3) = " << rwi(3) << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
rwi(3) = -3  
```  
  
##  <a name="reference_wrapper"></a> reference_wrapper::reference_wrapper  
 Erstellt ein Objekt vom Typ `reference_wrapper`.  
  
```  
reference_wrapper(Ty& val) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Ty`  
 Der zu umschließende Typ.  
  
 `val`  
 Der zu umschließende Wert.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor legt den gespeicherten Wert `ptr` auf `&val` fest.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__reference_wrapper_reference_wrapper.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="result_type"></a> reference_wrapper::result_type  
 Der schwache Ergebnistyp des umschlossenen Verweises.  
  
```  
typedef R result_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `result_type`-Typedefinition ist ein Synonym für den schwachen Ergebnistyp einer umschlossenen Funktion. Diese Typdefinition gilt nur für Funktionstypen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__reference_wrapper_result_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    typedef std::reference_wrapper<int (int)> Mywrapper;   
    Mywrapper rwi(neg);   
    Mywrapper::result_type val = rwi(3);   
  
    std::cout << "val = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
val = -3  
```  
  
##  <a name="type"></a> reference_wrapper::type  
 Der Typ des umschlossenen Verweises.  
  
```  
typedef Ty type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Typedef stellt ein Synonym für das Vorlagenargument `Ty`dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__reference_wrapper_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    typedef std::reference_wrapper<int> Mywrapper;   
    Mywrapper rwi(i);   
    Mywrapper::type val = rwi.get();   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [cref](../standard-library/functional-functions.md#cref)   
 [ref](../standard-library/functional-functions.md#ref)


