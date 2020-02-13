---
title: affinity_partitioner-Klasse
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: 0ae6bbee49d1b8873190a7054e55f65b40b31b13
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142876"
---
# <a name="affinity_partitioner-class"></a>affinity_partitioner-Klasse

Die `affinity_partitioner`-Klasse ist der `static_partitioner`-Klasse ähnlich, allerdings wird die Cacheaffinität dank der Auswahl, den Arbeitsthreads Unterbereiche zuzuordnen, verbessert. Sie kann die Leistung, bei erneutem Ausführen einer Schleife über dem gleichen Dataset, und wenn die Daten im Cache gespeichert werden können, erheblich verbessern. Beachten Sie, dass das gleiche `affinity_partitioner`-Objekt mit nachfolgenden Iterationen einer parallelen Schleife verwendet werden muss, die für ein bestimmtes Dataset ausgeführt wird, um vom Datenort zu profitieren.

## <a name="syntax"></a>Syntax

```cpp
class affinity_partitioner;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[affinity_partitioner](#ctor)|Erstellt ein `affinity_partitioner`-Objekt.|
|[~ affinity_partitioner-Dekonstruktor](#dtor)|Zerstört ein `affinity_partitioner` Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`affinity_partitioner`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppl. h

**Namespace:** Parallelität

## <a name="dtor"></a>~ affinity_partitioner

Zerstört ein `affinity_partitioner` Objekt.

```cpp
~affinity_partitioner();
```

## <a name="ctor"></a>affinity_partitioner

Erstellt ein `affinity_partitioner`-Objekt.

```cpp
affinity_partitioner();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
