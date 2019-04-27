---
title: nothrow_t-Struktur
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: 2313c436a1fd25149fa7ea72f122a6f323b40028
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223622"
---
# <a name="nothrowt-structure"></a>nothrow_t-Struktur

Die Struktur wird als Funktionsparameter für „operator new“ verwendet, um anzugeben, dass die Funktion zum Melden eines Zuordnungsfehlers keine Ausnahme auslösen, sondern einen NULL-Zeiger zurückgeben soll.

## <a name="syntax"></a>Syntax

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Hinweise

Die Struktur hilft dem Compiler beim Auswählen der richtigen Version des Konstruktors. [nothrow](../standard-library/new-functions.md#nothrow) ist ein Synonym für Objekte des Typs `std::nothrow_t`.

## <a name="example"></a>Beispiel

Beispiele zur Verwendung von `std::nothrow_t` als Funktionsparameter finden Sie unter [operator new](../standard-library/new-operators.md#op_new) und [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr).

## <a name="requirements"></a>Anforderungen

**Header:** \<new>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
