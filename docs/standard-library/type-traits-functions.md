---
title: '&lt;type_traits&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 3754af9a32ab1beeb4f3b9a783547bd081d57a46
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955830"
---
# <a name="lttypetraitsgt-functions"></a>&lt;type_traits&gt;-Funktionen

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|
|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a> is_assignable

Testet, ob der Wert *aus* Typ zugewiesen werden kann, um eine *zu* Typ.

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parameter

*Aktion*  
 Der Typ des Objekts, das die Zuweisung empfängt.

*From*  
 Der Typ des Objekts, das den Wert bereitstellt.

### <a name="remarks"></a>Hinweise

Der ausgewertete Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein. Beide *aus* und *zu* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="is_copy_assignable"></a> is_copy_assignable

Testet, ob der Typ durch Zuweisung kopiert werden kann.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parameter

*Ty*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die ein Kopierzuweisungsoperator verwendet, andernfalls er false enthält. Entspricht is_assignable\<Ty&, const Ty&>.

## <a name="is_copy_constructible"></a> is_copy_constructible

Testet, ob der Typ einen Kopierkonstruktor aufweist.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Parameter

*Ty*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die einen Kopierkonstruktor aufweist; andernfalls ist Sie false.

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

*T*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist ein Klassentyp, der einen standardmäßigen Konstruktor aufweist; andernfalls ist Sie false. Dies entspricht dem Prädikat `is_constructible<T>`. Typ *T* muss ein vollständiger Typ, **"void"**, oder ein Array mit Unbekannter Grenze.

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

*T*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Einem Typ kann eine Verschiebung zugewiesen werden, wenn ein rvalue-Verweis auf den Typ einem Verweis auf den Typ zugewiesen werden kann. Das Typprädikat entspricht `is_assignable<T&, T&&>`. Zu den Typen, denen eine Verschiebung zugewiesen werden kann, gehören verweisbare skalare Typen und Klassentypen, die entweder über vom Compiler generierte oder benutzerdefinierte Verschiebungszuweisungsoperatoren verfügen.

## <a name="is_move_constructible"></a> is_move_constructible

Testet, ob der Typ über einen Verschiebekonstruktor verfügt.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parameter

*T*  
 Der auszuwertende Typ.

### <a name="remarks"></a>Hinweise

Ein typprädikat, der auf "true" den Typ ergibt *T* mithilfe eines Verschiebevorgangs konstruiert werden kann. Dieses Prädikat entspricht `is_constructible<T, T&&>`.

## <a name="is_nothrow_move_assignable"></a> is_nothrow_move_assignable

Testet, ob der Typ über einen **nothrow**-Verschiebungszuweisungsoperator verfügt.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parameter

*Ty*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* verfügt über einen Nothrow bewegungszuweisungsoperator, andernfalls er false enthält.

## <a name="is_trivially_copy_assignable"></a> is_trivially_copy_assignable

Testet, ob der Typ einen trivialen Kopierzuweisungsoperator aufweist.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parameter

*T*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist eine Klasse, die einen trivialen Kopierzuweisungsoperator, andernfalls er false enthält.

Ein Zuweisungskonstruktor für eine Klasse *T* ist trivial, wenn er implizit angegeben ist. die Klasse *T* verfügt über keine virtuellen Funktionen, die Klasse *T* hat keine virtuellen Basen, die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Zuweisungsoperatoren und die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Zuweisungsoperatoren.

## <a name="is_trivially_move_assignable"></a> is_trivially_move_assignable

Testet, ob der Typ einen trivialen Verschiebezuweisungsoperator aufweist.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parameter

*Ty*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die einen trivialen verschiebezuweisungsoperator, andernfalls er false enthält.

Ein bewegungszuweisungsoperator für eine Klasse *Ty* ist trivial wenn:

Er wird impliziert bereitgestellt

die Klasse *Ty* verfügt über keine virtuellen Funktionen

die Klasse *Ty* hat keine virtuellen Basen

Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Verschiebungszuweisungsoperatoren

Die Klassen aller nicht statischen Datenmember des Typarrays der Klasse haben triviale Verschiebungszuweisungsoperatoren

## <a name="is_trivially_move_constructible"></a> is_trivially_move_constructible

Testet, ob der Typ einen trivialen Bewegungskonstruktor aufweist.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parameter

*Ty*  
 Der abzufragende Typ.

### <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die einen trivialen bewegungskonstruktor, andernfalls er false enthält.

Ein bewegungskonstruktor für eine Klasse *Ty* ist trivial wenn:

Er wird implizit deklariert.

die Parametertypen entsprechen den einer impliziten Deklaration

die Klasse *Ty* verfügt über keine virtuellen Funktionen

die Klasse *Ty* hat keine virtuellen Basen

die Klasse verfügt über keine flüchtigen nicht statischen Datenmember

alle direkten Basisklassen der Klasse *Ty* haben triviale bewegungskonstruktoren

die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Bewegungskonstruktoren

die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Bewegungskonstruktoren

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
