---
title: integral_constant Class, bool_constant-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::integral_constant
- XTR1COMMON/std::integral_constant
- type_traits/std::bool_constant
- XTR1COMMON/std::bool_constant
helpviewer_keywords:
- std::integral_constant [C++]
- std::bool_constant [C++]
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
ms.openlocfilehash: 9577ce51d4b0773f7b309fe3dc6dcb5820693dcb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689537"
---
# <a name="integral_constant-class-bool_constant-class"></a>integral_constant Class, bool_constant-Klasse

Wandelt einen Typ und einen Wert in eine Ganzzahlkonstante um.

## <a name="syntax"></a>Syntax

```cpp
template<class T, T v>
struct integral_constant {
   static constexpr T value = v;
   typedef T value_type;
   typedef integral_constant<T, v> type;
   constexpr operator value_type() const noexcept;
   constexpr value_type operator()() const noexcept;
   };
```

### <a name="parameters"></a>Parameter

*T* \
Der Typ der Konstante.

*v* \
Der Wert der Konstante.

## <a name="remarks"></a>Hinweise

Die `integral_constant`-Klassen Vorlage, wenn Sie mit einem ganzzahligen Typ *t* und einem Wert *v* dieses Typs spezialisiert ist, stellt ein Objekt dar, das eine Konstante dieses ganzzahligen Typs mit dem angegebenen Wert enthält. Beim Member `type` handelt es sich um ein Alias des erstellten Vorlagenspezialisierungstypen, und der Member `value` hält den Wert *v*, der beim Erstellen der Spezialisierung verwendet wurde.

Die `bool_constant`-Klassen Vorlage ist eine explizite partielle Spezialisierung von `integral_constant`, die **bool** als *t* -Argument verwendet.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__integral_constant.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "integral_constant<int, 5> == "
        << std::integral_constant<int, 5>::value << std::endl;
    std::cout << "integral_constant<bool, false> == " << std::boolalpha
        << std::integral_constant<bool, false>::value << std::endl;

    return (0);
    }
```

```Output
integral_constant<int, 5> == 5
integral_constant<bool, false> == false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[false_type](../standard-library/type-traits-typedefs.md#false_type) \
[true_type](../standard-library/type-traits-typedefs.md#true_type)
