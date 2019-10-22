---
title: '&lt;memory_resource &gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: 752396bb06b292ce29b7c6cd292287955b6066a7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687713"
---
# <a name="ltmemory_resourcegt"></a>&lt;memory_resource &gt;

Definiert die Container-Klassen Vorlage memory_resource und deren unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

```cpp
#include <memory_resource>
```

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/memory-resource-operators.md#op_neq)|Testet, ob das memory_resource-Objekt links vom Operator ungleich dem memory_resource-Objekt rechts vom Operator ist.|
|[operator==](../standard-library/memory-resource-operators.md#op_eq_eq)|Testet, ob das memory_resource-Objekt links vom Operator gleich dem memory_resource-Objekt rechts vom Operator ist.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|||
|-|-|
|[polymorphic_allocator](../standard-library/memory-resource-functions.md#poly_alloc)||

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
|[memory_resource-Klasse](../standard-library/memory-resource-class.md)||
|[monotonic_buffer_resource-Klasse](../standard-library/monotonic-buffer-resource-class.md)||
|[pool_options-Struktur](../standard-library/pool-options-structure.md)||
|[synchronized_pool_resource-Klasse](../standard-library/synchronized-pool-resource-class.md)||
|[unsynchronized_pool_resource-Klasse](../standard-library/unsynchronized-pool-resource-class.md)||

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
