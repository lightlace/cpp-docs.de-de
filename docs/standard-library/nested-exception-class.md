---
title: Nested_exception-Klasse
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: a568a8d9a3817883656406d63c3dd948539bb385
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268522"
---
# <a name="nestedexception-class"></a>Nested_exception-Klasse

Die Klasse beschreibt eine Ausnahme für die Verwendung mit mehrfacher Vererbung. Die derzeit behandelte Ausnahme erfasst und speichert sie für die spätere Verwendung.

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
|[rethrow_nested](#rethrow_nested)|Die gespeicherte-Ausnahme ausgelöst.|
|[nested_ptr](#nested_ptr)|Gibt die gespeicherte Ausnahme zurück.|

### <a name="op_as"></a> Operator =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>Rückgabewert

Die gespeicherte Ausnahme, die von diesem erfasste `nested_exception` Objekt.

### <a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>Hinweise

Wenn `nested_ptr()` gibt einen null-Zeiger die Funktionsaufrufe `std::terminate()`. Andernfalls löst er die gespeicherte Ausnahme, die von erfasst `*this`.

## <a name="requirements"></a>Anforderungen

**Header:** \<exception>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[exception-Klasse](../standard-library/exception-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
