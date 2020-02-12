---
title: simple_partitioner-Klasse
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 503f36b90c5eb3319f9aa2d56528172ffa95bb11
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142497"
---
# <a name="simple_partitioner-class"></a>simple_partitioner-Klasse

Die `simple_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in Blöcke unterteilt, sodass jeder Block mindestens die von der Segmentgröße angegebene Anzahl von Iterationen enthält.

## <a name="syntax"></a>Syntax

```cpp
class simple_partitioner;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[simple_partitioner](#ctor)|Erstellt ein `simple_partitioner`-Objekt.|
|[~ simple_partitioner-Dekonstruktor](#dtor)|Zerstört ein `simple_partitioner` -Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`simple_partitioner`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppl. h

**Namespace:** Parallelität

## <a name="dtor"></a>~ simple_partitioner

Zerstört ein `simple_partitioner` -Objekt.

```cpp
~simple_partitioner();
```

## <a name="ctor"></a>simple_partitioner

Erstellt ein `simple_partitioner`-Objekt.

```cpp
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Parameter

*_Chunk_size*<br/>
Die minimale Partitionsgröße.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
