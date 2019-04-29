---
title: pointer_traits-Struktur
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
ms.openlocfilehash: b661d4b36ce48a08faba6638c5114f3f4e6981a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370384"
---
# <a name="pointertraits-struct"></a>pointer_traits-Struktur

Stellt Informationen bereit, die für ein Objekt der Vorlagenklasse `allocator_traits` erforderlich sind, um eine Zuweisung mit Zeigertyp `Ptr` zu beschreiben.

## <a name="syntax"></a>Syntax

```cpp
template <class Ptr>
struct pointer_traits;
```

## <a name="remarks"></a>Hinweise

Ptr kann ein unformatierter Zeiger vom Typ `Ty *` oder eine Klasse mit den folgenden Eigenschaften sein.

```cpp
struct Ptr
   { // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj);
   // optional
   };
```

### <a name="typedefs"></a>Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`typedef T2 difference_type`|Der Typ `T2` ist `Ptr::difference_type`, wenn dieser Typ vorhanden ist, andernfalls ist er `ptrdiff_t`. Wenn `Ptr` ein unformatierter Zeiger ist, ist der Typ `ptrdiff_t`.|
|`typedef T1 element_type`|Der Typ `T1` ist `Ptr::element_type`, wenn dieser Typ vorhanden ist, andernfalls ist er `Ty`. Wenn `Ptr` ein unformatierter Zeiger ist, ist der Typ `Ty`.|
|`typedef Ptr pointer`|Der Typ lautet `Ptr`.|

### <a name="structs"></a>Strukturen

|Name|Beschreibung|
|----------|-----------------|
|`pointer_traits::rebind`|Versucht, den zugrunde liegenden Zeigertyp in einen angegebenen Typ zu konvertieren.|

### <a name="methods"></a>Methoden

|Name|Beschreibung|
|----------|-----------------|
|[pointer_to](#pointer_to)|Konvertiert einen beliebigen Verweis auf ein Objekt der Klasse `Ptr`.|

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="pointer_to"></a> pointer_to

Statische Methode, die `Ptr::pointer_to(obj)` zurückgibt, wenn diese Funktion vorhanden ist. Andernfalls ist es nicht möglich einen beliebigen Verweis auf ein Objekt der Klasse `Ptr` zu konvertieren. Wenn `Ptr` ein unformatierter Zeiger ist, gibt diese Methode `addressof(obj)` zurück.

```cpp
static pointer pointer_to(element_type& obj);
```

## <a name="see-also"></a>Siehe auch

[\<memory>](../standard-library/memory.md)<br/>
[allocator_traits-Klasse](../standard-library/allocator-traits-class.md)<br/>
