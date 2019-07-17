---
title: '&lt;new&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 80123bc35422984ef92bdba6da45052d3461b1d7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245166"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

## <a name="hardware_constructive_interference_size"></a> hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Hinweise

Diese Zahl ist die maximale empfohlene Größe zusammenhängender Arbeitsspeicher, die von zwei Objekten, die mit der zeitlichen Lokalität zugegriffen wird, durch parallele Threads belegt wird. Es muss mindestens sein `alignof(max_align_t)`.

### <a name="example"></a>Beispiel

```cpp
struct together { 
    atomic<int> dog;
    int puppy;
};

struct kennel {
    // Other data members...
    alignas(sizeof(together)) together pack;
    // Other data members...
};

static_assert(sizeof(together) <= hardware_constructive_interference_size);
```

## <a name="hardware_destructive_interference_size"></a> hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Hinweise

Diese Zahl ist die minimale empfohlene Offset zwischen zwei gleichzeitig Zugriff auf Objekte zu zusätzlichen Leistungseinbußen aufgrund von Konflikten eingeführt, durch die Implementierung zu vermeiden. Es muss mindestens sein `alignof(max_align_t)`.

### <a name="example"></a>Beispiel

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a> new_handler

Der Typ verweist auf eine Funktion, die als neuer Handler geeignet ist.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Hinweise

Diese Art von Handler-Funktion wird aufgerufen, indem **new-Operator** oder `operator new[]` Wenn sie eine Anforderung für zusätzlichen Speicher erfüllen nicht möglich.

### <a name="example"></a>Beispiel

Unter [set_new_handler](../standard-library/new-functions.md#set_new_handler) finden Sie ein Beispiel mit `new_handler` als Rückgabewert.
