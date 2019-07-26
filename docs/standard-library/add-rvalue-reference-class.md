---
title: add_rvalue_reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_rvalue_reference
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
ms.openlocfilehash: 64694f2428c1dd536df4d242a17f3f011cfb290c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456523"
---
# <a name="addrvaluereference-class"></a>add_rvalue_reference-Klasse

Erstellt einen rvalue-Verweistyp des Vorlagenparameters, wenn es sich dabei um einen Objekt- oder Funktionstyp handelt. Ansonsten ist der Typ aufgrund der Semantik der Verweisreduzierung der Gleiche wie der Vorlagenparameter.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Die `add_rvalue_reference` -Klasse verfügt über einen `type`Member mit dem Namen, bei dem es sich um einen Alias für den Typ eines Rvalue-Verweises auf den Vorlagen Parameter *T*handelt. Die Semantik der Verweis Reduzierung impliziert, dass für nicht-Objekt-und nicht-Funktions Typen t `T&&` ein *t*ist. Wenn *T* beispielsweise ein Lvalue-Verweistyp ist, `add_rvalue_reference<T>::type` ist der lvalue-Verweistyp und kein rvalue-Verweis.

Zur einfacheren Handhabung definiert `add_rvalue_reference_t` `type` `add_rvalue_reference`type_traits > eine hilfsvorlage,, die das Element von Alias Aliase. \<

## <a name="example"></a>Beispiel

Dieses Codebeispiel verwendet static_assert, um anzuzeigen, wie rvalue-Verweistypen mithilfe von `add_rvalue_reference` und `add_rvalue_reference_t` erstellt werden, und wie das Ergebnis von `add_rvalue_reference` eines rvalue-Verweistyps kein rvalue-Verweis ist, sondern auf einen lvalue-Typ reduziert wird.

```cpp
// ex_add_rvalue_reference.cpp
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp
#include <type_traits>
#include <iostream>
#include <string>

using namespace std;
int main()
{
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,
        "Expected add_rvalue_reference_t<string> to be string&&");
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,
        "Expected add_rvalue_reference_t<string*> to be string*&&");
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,
        "Expected add_rvalue_reference_t<string&> to be string&");
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,
        "Expected add_rvalue_reference_t<string&&> to be string&&");
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;
    return 0;
}

/*Output:
All static_assert tests of add_rvalue_reference passed.
*/
```

## <a name="requirements"></a>Anforderungen

Header: \<type_traits>

Namespace: Std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[add_lvalue_reference-Klasse](../standard-library/add-lvalue-reference-class.md)\
[is_rvalue_reference-Klasse](../standard-library/is-rvalue-reference-class.md)
