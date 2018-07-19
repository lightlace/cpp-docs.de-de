---
title: is_pod-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c655ea4adec0364f35d0b43c637eae9c270cdb0e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962064"
---
# <a name="ispod-class"></a>is_pod-Klasse

Testet, ob der Typ POD ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_pod;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

`is_pod<T>::value` ist **"true"** Wenn der Typ *T* Plain Old Data (POD) ist. Andernfalls ist es **"false"**.

Arithmetische Typen, Enumerationstypen, Zeigertypen und Zeiger auf Membertypen sind POD.

Eine cv-qualifizierte Version eines POD-Typs ist selbst ein POD-Typ.

Ein Array von POD ist selbst POD.

Eine Struktur oder Union, all deren nicht statische Datenmember POD sind, ist selbst POD, wenn sie Folgendes aufweist:

- Keine benutzerdeklarierten Konstruktoren

- Keine privaten oder geschützten nicht statischen Datenmember

- Keine Basisklassen

- Keine virtuellen Funktionen

- Keine nicht statischen Datenmember des Verweistyps

- Keinen benutzerdefinierten Kopierzuweisungsoperator

- Keinen benutzerdefinierten Destruktor

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

[<type_traits>](../standard-library/type-traits.md)<br/>
