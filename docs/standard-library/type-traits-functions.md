---
title: '&lt;type_traits&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
- type_traits/std::is_copy_assignable
- type_traits/std::is_copy_constructible
- type_traits/std::is_default_constructible
- type_traits/std::is_move_assignable
- type_traits/std::is_move_constructible
- type_traits/std::is_nothrow_move_assignable
- type_traits/std::is_trivially_copy_assignable
- type_traits/std::is_trivially_move_assignable
- type_traits/std::is_trivially_move_constructible
ms.assetid: dce4492f-f3e4-4d5e-bdb4-5875321254ec
caps.latest.revision: 13
manager: ghogen
helpviewer_keywords:
- std::is_assignable
- std::is_copy_assignable
- std::is_copy_constructible
- std::is_default_constructible
- std::is_move_assignable
- std::is_move_constructible
- std::is_nothrow_move_assignable
- std::is_trivially_copy_assignable
- std::is_trivially_move_assignable
- std::is_trivially_move_constructible
ms.openlocfilehash: 1d2db7b749bfc4266a613b872e32965ff16a4c4c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="lttypetraitsgt-functions"></a>&lt;type_traits&gt;-Funktionen

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|
|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a> is_assignable

Testet, ob ein Wert des `From`-Typs einem `To`-Typ zugewiesen werden kann.

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parameter

In den Typ des Objekts, das die Zuweisung empfängt.

Vom Typ des Objekts, das den Wert bereitstellt.

### <a name="remarks"></a>Hinweise

Der ausgewertete Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein. `From` und `To` müssen beide vollständige Typen sein, `void`, oder Arrays mit unbekannter Grenze.

## <a name="is_copy_assignable"></a> is_copy_assignable

Testet, ob der Typ durch Zuweisung kopiert werden kann.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ eine Klasse ist, die einen Kopierzuweisungsoperator aufweist; andernfalls „false“. Entsprechung zu is_assignable\<Ty&, const Ty&>.

## <a name="is_copy_constructible"></a> is_copy_constructible

Testet, ob der Typ einen Kopierkonstruktor aufweist.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ eine Klasse ist, die einen Kopierkonstruktor aufweist; andernfalls „false“.

### <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}

```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="is_default_constructible"></a> is_default_constructible

Testet, ob ein Typ einen Standardkonstruktor besitzt.

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der Typ `T` ein Klassentyp ist, der einen trivialen Konstruktor aufweist; andernfalls „false“. Dies entspricht dem Prädikat `is_constructible<T>`. Typ `T` muss ein vollständiger Typ, `void`oder ein Array mit unbekannter Grenze sein.

### <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}

```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="is_move_assignable"></a> is_move_assignable

Prüft, ob dem Typ eine Verschiebung zugewiesen werden kann.

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Einem Typ kann eine Verschiebung zugewiesen werden, wenn ein rvalue-Verweis auf den Typ einem Verweis auf den Typ zugewiesen werden kann. Das Typprädikat entspricht `is_assignable<T&, T&&>`. Zu den Typen, denen eine Verschiebung zugewiesen werden kann, gehören verweisbare skalare Typen und Klassentypen, die entweder über vom Compiler generierte oder benutzerdefinierte Verschiebungszuweisungsoperatoren verfügen.

## <a name="is_move_constructible"></a> is_move_constructible

Testet, ob der Typ über einen Verschiebekonstruktor verfügt.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parameter

T der Typ ausgewertet werden soll

### <a name="remarks"></a>Hinweise

Ein Typprädikat, das TRUE ausgewertet wird, wenn der Typ `T` mithilfe eines Verschiebevorgangs konstruiert werden kann. Dieses Prädikat entspricht `is_constructible<T, T&&>`.

## <a name="is_nothrow_move_assignable"></a> is_nothrow_move_assignable

Testet, ob der Typ über einen **nothrow**-Verschiebungszuweisungsoperator verfügt.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ einen nothrow-Verschiebungszuweisungsoperator aufweist; andernfalls „false“.

## <a name="is_trivially_copy_assignable"></a> is_trivially_copy_assignable

Testet, ob der Typ einen trivialen Kopierzuweisungsoperator aufweist.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist TRUE, wenn der `T`-Typ eine Klasse ist, die einen Kopierzuweisungsoperator aufweist; andernfalls FALSE.

Ein Zuweisungskonstruktor für eine Klasse `T` ist trivial, wenn er implizit angegeben ist. Die Klasse `T` verfügt über keine virtuellen Funktionen und die Klasse `T` hat keine virtuellen Basen. Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Zuweisungsoperatoren und die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Zuweisungsoperatoren.

## <a name="is_trivially_move_assignable"></a> is_trivially_move_assignable

Testet, ob der Typ einen trivialen Verschiebezuweisungsoperator aufweist.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ eine Klasse ist, die einen Verschiebungszuweisungsoperator aufweist; andernfalls „false“.

Ein Verschiebungszuweisungsoperator für eine `Ty`-Klasse ist in den folgenden Fällen trivial:

Er wird impliziert bereitgestellt

Die `Ty`-Klasse hat keine virtuellen Funktionen

Die `Ty`-Klasse hat keine virtuellen Basen

Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Verschiebungszuweisungsoperatoren

Die Klassen aller nicht statischen Datenmember des Typarrays der Klasse haben triviale Verschiebungszuweisungsoperatoren

## <a name="is_trivially_move_constructible"></a> is_trivially_move_constructible

Testet, ob der Typ einen trivialen Bewegungskonstruktor aufweist.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist TRUE, wenn der `Ty` Typ eine Klasse ist, die einen trivialen Bewegungskonstruktor aufweist; andernfalls FALSE.

Ein Bewegungskonstruktor für eine `Ty`-Klasse ist trivial, wenn:

Er wird implizit deklariert.

die Parametertypen entsprechen den einer impliziten Deklaration

die `Ty`-Klasse hat keine virtuellen Funktionen

die `Ty`-Klasse hat keine virtuellen Basen

die Klasse verfügt über keine flüchtigen nicht statischen Datenmember

alle direkten Basisklassen der `Ty`-Klasse weisen triviale Bewegungskonstruktoren auf

die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Bewegungskonstruktoren

die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Bewegungskonstruktoren

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
