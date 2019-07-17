---
title: Default_delete-Struktur
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: e9e1fcc68539e55486f4ea27e6dd5c49bed11fdf
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269262"
---
# <a name="defaultdelete-struct"></a>Default_delete-Struktur

Ein vordefiniertes Funktionsobjekt, das den Divisionsvorgang (`operator/`) auf den Argumenten ausführt.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[default_delete](#default_delete)|Der Konstruktor für Objekte des Typs `default_delete`.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator()](#op_paren)|Ein verweisoperator, den Zugriff auf `default_delete`.|

## <a name="default_delete"></a> default_delete

Der Konstruktor für Objekte des Typs `default_delete`.

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="op_paren"></a> Operator()

Ein verweisoperator, den Zugriff auf `default_delete`.

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>Siehe auch

[\<memory>](../standard-library/memory.md)
