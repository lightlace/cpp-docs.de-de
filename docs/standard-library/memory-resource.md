---
title: '&lt;memory_resource&gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: b5957412d2beff0dc709dc71a77834f13eeacb41
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269342"
---
# <a name="ltmemoryresourcegt"></a>&lt;memory_resource&gt;

Definiert die Container-Vorlage Klasse Memory_resource und deren unterstützenden Vorlagen.

## <a name="syntax"></a>Syntax

```cpp
#include <memory_resource>
```

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/memory-resource-operators.md#op_neq)|Testet, ob das Memory_resource-Objekt links vom Operator ist nicht gleich dem Memory_resource-Objekt auf der rechten Seite ist.|
|[operator==](../standard-library/memory-resource-operators.md#op_eq_eq)|Testet, ob das Memory_resource-Objekt auf der linken Seite des Operators gleich dem Memory_resource-Objekt auf der rechten Seite ist.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|||
|-|-|
|[der polymorphic_allocator](../standard-library/memory-resource-functions.md#poly_alloc)||

### <a name="functions"></a>Funktionen

|||
|-|-|
|[get_default_resource](../standard-library/memory-resource-functions.md#get_default)||
|[new_delete_resource](../standard-library/memory-resource-functions.md#new_delete)||
|[null_memory_resource](../standard-library/memory-resource-functions.md#null_memory)||
|[set_default_resource](../standard-library/memory-resource-functions.md#set_default)||

### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|[Memory_resource-Klasse](../standard-library/memory-resource-class.md)||
|[Monotonic_buffer_resource-Klasse](../standard-library/monotonic-buffer-resource-class.md)||
|[Pool_options-Struktur](../standard-library/pool-options-structure.md)||
|[Synchronized_pool_resource-Klasse](../standard-library/synchronized-pool-resource-class.md)||
|[Unsynchronized_pool_resource-Klasse](../standard-library/unsynchronized-pool-resource-class.md)||

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
