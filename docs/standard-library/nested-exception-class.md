---
title: nested_exception-Klasse
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 5741b3aa255f915500f5fe79ab5374c8c86f8814
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460177"
---
# <a name="nestedexception-class"></a>nested_exception-Klasse

Die Klasse beschreibt eine Ausnahme für die Verwendung mit Mehrfachvererbung. Die aktuell behandelte Ausnahme wird erfasst und zur späteren Verwendung gespeichert.

## <a name="syntax"></a>Syntax

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator=](#op_as)||

### <a name="functions"></a>Funktionen

|||
|-|-|
|[rethrow_nested](#rethrow_nested)|Löst die gespeicherte Ausnahme aus.|
|[nested_ptr](#nested_ptr)|Gibt die gespeicherte Ausnahme zurück.|

### <a name="op_as"></a>Operator =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a>nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Rückgabewert

Die von diesem `nested_exception` -Objekt erfasste gespeicherte Ausnahme.

### <a name="rethrow_nested"></a>rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Hinweise

Wenn `nested_ptr()` einen NULL-Zeiger zurückgibt, ruft `std::terminate()`die Funktion auf. Andernfalls wird die von `*this`erfasste gespeicherte Ausnahme ausgelöst.

## <a name="requirements"></a>Anforderungen

**Header:** \<exception>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Exception-Klasse](../standard-library/exception-class.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
