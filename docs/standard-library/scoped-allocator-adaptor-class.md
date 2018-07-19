---
title: scoped_allocator_adaptor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- scoped_allocator/std::scoped_allocator_adaptor
- scoped_allocator/std::scoped_allocator_adaptor::rebind Struct
- scoped_allocator/std::scoped_allocator_adaptor::allocate
- scoped_allocator/std::scoped_allocator_adaptor::construct
- scoped_allocator/std::scoped_allocator_adaptor::deallocate
- scoped_allocator/std::scoped_allocator_adaptor::destroy
- scoped_allocator/std::scoped_allocator_adaptor::inner_allocator
- scoped_allocator/std::scoped_allocator_adaptor::max_size
- scoped_allocator/std::scoped_allocator_adaptor::outer_allocator
- scoped_allocator/std::scoped_allocator_adaptor::select_on_container_copy_construction
dev_langs:
- C++
helpviewer_keywords:
- std::scoped_allocator_adaptor
- std::scoped_allocator_adaptor::allocate
- std::scoped_allocator_adaptor::construct
- std::scoped_allocator_adaptor::deallocate
- std::scoped_allocator_adaptor::destroy
- std::scoped_allocator_adaptor::inner_allocator
- std::scoped_allocator_adaptor::max_size
- std::scoped_allocator_adaptor::outer_allocator
- std::scoped_allocator_adaptor::select_on_container_copy_construction
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7025e0d52aa882c26e2785279626959ca6b29ac1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962929"
---
# <a name="scopedallocatoradaptor-class"></a>scoped_allocator_adaptor-Klasse

Stellt einen Satz von Zuweisern dar.

## <a name="syntax"></a>Syntax

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse kapselt einen Satz von einem oder mehreren Zuweisern. Jede Klasse hat einen äußersten Zuweiser vom Typ `outer_allocator_type`, ein Synonym für `Outer`, das eine öffentliche Basis des `scoped_allocator_adaptor`-Objekts darstellt. Mit `Outer` wird der von einem Container zu verwendende Speicher zugewiesen. Sie erhalten einen Verweis auf dieses Zuweiserbasisobjekt, indem Sie `outer_allocator` aufrufen.

Der Rest des Satzes weist Typ `inner_allocator_type` auf. Mit einem inneren Zuweiser wird Speicher für Elemente in einem Container zugewiesen. Sie erhalten einen Verweis auf das gespeicherte Objekt dieses Typs, indem Sie `inner_allocator` aufrufen. Wenn `Inner...` nicht leer ist, weist `inner_allocator_type` den Typ `scoped_allocator_adaptor<Inner...>` auf, und `inner_allocator` kennzeichnet ein Memberobjekt. Andernfalls weist `inner_allocator_type` den Typ `scoped_allocator_adaptor<Outer>` auf, und `inner_allocator` kennzeichnet das gesamte Objekt.

Der Satz verhält sich so, als hätte er eine beliebige Tiefe, wobei nach Bedarf der innerste gekapselte Zuweiser repliziert wird.

Mehrere Konzepte, die nicht Teil der sichtbaren Benutzeroberfläche sind, helfen bei der Beschreibung des Verhaltens dieser Vorlagenklasse. Ein *äußerster Zuweiser* vermittelt alle Aufrufe an die construct- und die destroy-Methode. Er wird durch die rekursive Funktion `OUTERMOST(X)` definiert, wobei `OUTERMOST(X)` eines der folgenden Elemente ist.

- Wenn `X.outer_allocator()` wohlgeformt ist, ist `OUTERMOST(X)` gleich `OUTERMOST(X.outer_allocator())`.

- Andernfalls lautet `OUTERMOST(X)` `X`.

Drei Typen werden zum Zwecke der Darstellung generiert:

|Typ|Beschreibung|
|----------|-----------------|
|`Outermost`|Der `OUTERMOST(*this)`-Typ.|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Konstruktoren

|name|Beschreibung|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|Erstellt ein `scoped_allocator_adaptor`-Objekt.|

### <a name="typedefs"></a>Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`const_pointer`|Dieser Typ ist ein Synonym für den `const_pointer`, der dem Zuweiser `Outer` zugeordnet ist.|
|`const_void_pointer`|Dieser Typ ist ein Synonym für den `const_void_pointer`, der dem Zuweiser `Outer` zugeordnet ist.|
|`difference_type`|Dieser Typ ist ein Synonym für den `difference_type`, der dem Zuweiser `Outer` zugeordnet ist.|
|`inner_allocator_type`|Dieser Typ ist ein Synonym für den Typ des geschachtelten Adapters `scoped_allocator_adaptor<Inner...>`.|
|`outer_allocator_type`|Dieser Typ ist ein Synonym für den Typ des Basiszuweisers `Outer`.|
|`pointer`|Dieser Typ ist ein Synonym für den `pointer`, der dem Zuweiser `Outer` zugeordnet ist.|
|`propagate_on_container_copy_assignment`|Der Typ enthält TRUE nur dann, wenn `Outer_traits::propagate_on_container_copy_assignment` oder `inner_allocator_type::propagate_on_container_copy_assignment` TRUE enthalten.|
|`propagate_on_container_move_assignment`|Der Typ enthält TRUE nur dann, wenn `Outer_traits::propagate_on_container_move_assignment` oder `inner_allocator_type::propagate_on_container_move_assignment` TRUE enthalten.|
|`propagate_on_container_swap`|Der Typ enthält TRUE nur dann, wenn `Outer_traits::propagate_on_container_swap` oder `inner_allocator_type::propagate_on_container_swap` TRUE enthalten.|
|`size_type`|Dieser Typ ist ein Synonym für den `size_type`, der dem Zuweiser `Outer` zugeordnet ist.|
|`value_type`|Dieser Typ ist ein Synonym für den `value_type`, der dem Zuweiser `Outer` zugeordnet ist.|
|`void_pointer`|Dieser Typ ist ein Synonym für den `void_pointer`, der dem Zuweiser `Outer` zugeordnet ist.|

### <a name="structs"></a>Strukturen

|name|Beschreibung|
|----------|-----------------|
|[scoped_allocator_adaptor::rebind Struct](#rebind_struct)|Definiert den Typ `Outer::rebind\<Other>::other` als Synonym für `scoped_allocator_adaptor\<Other, Inner...>`.|

### <a name="methods"></a>Methoden

|Name|Beschreibung|
|----------|-----------------|
|[allocate](#allocate)|Weist Speicher mithilfe des `Outer`-Zuweisers zu|
|[construct](#construct)|Erstellt ein Objekt|
|[deallocate](#deallocate)|Hebt die Zuweisung von Objekten mithilfe des äußeren Zuweisers auf|
|[destroy](#destroy)|Zerstört ein angegebenes Objekt|
|[inner_allocator](#inner_allocator)|Ruft einen Verweis auf das gespeicherte Objekt vom Typ `inner_allocator_type` ab|
|[max_size](#max_size)|Bestimmt die maximale Anzahl von Objekten, die vom äußeren Zuweiser zugewiesen werden kann.|
|[outer_allocator](#outer_allocator)|Ruft einen Verweis auf das gespeicherte Objekt vom Typ `outer_allocator_type` ab|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Erstellt ein neues `scoped_allocator_adaptor`-Objekt mit jedem gespeicherten Zuweiserobjekt, das durch Aufrufen von `select_on_container_copy_construction` für jeden entsprechenden Zuweiser initialisiert wird.|

## <a name="requirements"></a>Anforderungen

**Header:** \<scoped_allocator>

**Namespace:** std

## <a name="allocate"></a>  scoped_allocator_adaptor:: Allocate

Weist Speicher mithilfe des `Outer`-Zuweisers zu

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Parameter

*Anzahl* die Anzahl der Elemente, die für die ist ausreichend Speicherplatz zugeordnet werden.

*Hinweis* ein Zeiger, der möglicherweise das zuweiserobjekt unterstützt, dazu sucht er die Adresse eines vor der Anforderung zugewiesenen Objekts.

### <a name="return-value"></a>Rückgabewert

Die erste Memberfunktion gibt `Outer_traits::allocate(outer_allocator(), count)` zurück. Die zweite Memberfunktion gibt `Outer_traits::allocate(outer_allocator(), count, hint)` zurück.

## <a name="construct"></a>  scoped_allocator_adaptor:: Construct

Erstellt ein Objekt

```cpp
template <class Ty, class... Atypes>
void construct(Ty* ptr, Atypes&&... args);

template <class Ty1, class Ty2, class... Atypes1, class... Atypes2>
void construct(pair<Ty1, Ty2>* ptr, piecewise_construct_t,
    tuple<Atypes1&&...>
first, tuple<Atypes1&&...> second);

template <class Ty1, class Ty2>
void construct(pair<Ty1, Ty2>* ptr);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr,
    class Uy1&& first, class Uy2&& second);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, const pair<Uy1, Uy2>& right);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, pair<Uy1, Uy2>&& right);
```

### <a name="parameters"></a>Parameter

*PTR* ein Zeiger auf die Speicheradresse, in dem das Objekt ist, erstellt werden soll.

*Args* eine Liste von Argumenten.

*erste* ein Objekt des ersten Typs in einem Paar.

*zweite* ein Objekt des zweiten Typs in einem Paar.

*richtige* ein vorhandenes Objekt verschoben oder kopiert werden.

### <a name="remarks"></a>Hinweise

Die erste Methode erstellt das Objekt am *Ptr* durch Aufrufen von `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`, wobei `xargs...` ist eine der folgenden.

- Wenn `uses_allocator<Ty, inner_allocator_type>` FALSE enthält, dann ist `xargs...` gleich `args...`.

- Wenn `uses_allocator<Ty, inner_allocator_type>` und `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` TRUE enthalten, ist `xargs...` gleich `allocator_arg, inner_allocator(), args...`.

- Wenn `uses_allocator<Ty, inner_allocator_type>` und `is_constructible<Ty, args..., inner_allocator()>` TRUE enthalten, ist `xargs...` gleich `args..., inner_allocator()`.

Die zweite Methode erstellt das paarobjekt in *Ptr* durch Aufrufen von `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`, wobei `xargs...` ist `first...` geändert wie in der Liste oben und `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`, wobei `xargs...` ist `second...` geändert wie in der obigen Liste.

Die dritte Methode verhält sich wie `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)`.

Die vierte Methode verhält sich wie `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))`.

Die fünfte Methode verhält sich wie `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))`.

Die sechste Methode verhält sich wie `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))`.

## <a name="deallocate"></a>  scoped_allocator_adaptor:: DEALLOCATE

Hebt die Zuweisung von Objekten mithilfe des äußeren Zuweisers auf

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parameter

*PTR* ein Zeiger auf die Startposition der Objekte aufgehoben werden.

*Anzahl* die Anzahl der Objekte beim Aufheben der Zuordnung.

## <a name="destroy"></a>  scoped_allocator_adaptor:: Destroy

Zerstört ein angegebenes Objekt

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>Parameter

*PTR* ein Zeiger auf das Objekt zerstört werden soll.

### <a name="return-value"></a>Rückgabewert

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="inner_allocator"></a>  scoped_allocator_adaptor:: inner_allocator

Ruft einen Verweis auf das gespeicherte Objekt vom Typ `inner_allocator_type` ab

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das gespeicherte Objekt vom Typ `inner_allocator_type`

## <a name="max_size"></a>  scoped_allocator_adaptor:: max_size

Bestimmt die maximale Anzahl von Objekten, die vom äußeren Zuweiser zugewiesen werden kann.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Rückgabewert

`Outer_traits::max_size(outer_allocator())`

## <a name="outer_allocator"></a>  scoped_allocator_adaptor:: outer_allocator

Ruft einen Verweis auf das gespeicherte Objekt vom Typ `outer_allocator_type` ab

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das gespeicherte Objekt vom Typ `outer_allocator_type`

## <a name="rebind_struct"></a> scoped_allocator_adaptor::rebind-Struct

Definiert den Typ `Outer::rebind\<Other>::other` als Synonym für `scoped_allocator_adaptor\<Other, Inner...>`.

Struktur binden {Typedef Other_traits::rebind\<andere > Other_alloc; Typedef Scoped_allocator_adaptor\<Other_alloc, innere... > andere;};

## <a name="scoped_allocator_adaptor"></a> scoped_allocator_adaptor::scoped_allocator_adaptor-Konstruktor

Erstellt ein `scoped_allocator_adaptor`-Objekt.

```cpp
scoped_allocator_adaptor();

scoped_allocator_adaptor(const scoped_allocator_adaptor& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
 const scoped_allocator_adaptor<Outer2, Inner...>& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
 scoped_allocator_adaptor<Outer2, Inner...>&& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(Outer2&& al,
    const Inner&... rest) noexcept;
```

### <a name="parameters"></a>Parameter

*richtige* bestehendes `scoped_allocator_adaptor`.

*Al* eine vorhandener zuweiser, der als äußerer zuweiser verwendet werden.

*Rest* eine Liste von zuweisern, die als innere zuweiser verwendet werden.

### <a name="remarks"></a>Hinweise

Der erste Konstruktorstandard erstellt seine gespeicherten Zuweiserobjekte. Jeder der nächsten drei Konstruktoren erstellt seine gespeicherten zuweiserobjekte aus den entsprechenden Objekten in *rechten*. Der letzte Konstruktor erstellt seine gespeicherten Zuweiserobjekte aus den entsprechenden Argumenten in der Argumentliste.

## <a name="select_on_container_copy_construction"></a>  scoped_allocator_adaptor:: select_on_container_copy_construction

Erstellt ein neues `scoped_allocator_adaptor`-Objekt mit jedem gespeicherten Zuweiserobjekt, das durch Aufrufen von `select_on_container_copy_construction` für jeden entsprechenden Zuweiser initialisiert wird.

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())` zurück. Das Ergebnis ist ein neues `scoped_allocator_adaptor` Objekt mit jedem gespeicherten zuweiserobjekt, das initialisiert, durch den Aufruf `al.select_on_container_copy_construction()` für den entsprechenden zuweiser *al*.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
