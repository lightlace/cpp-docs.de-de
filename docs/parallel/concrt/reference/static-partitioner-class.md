---
title: static_partitioner-Klasse
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: 7a58daa27bc7a2f51f78a3068a2f152979ffdd72
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142681"
---
# <a name="static_partitioner-class"></a>static_partitioner-Klasse

Die `static_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Der Partitionierer dividiert den Bereich in so viele Blöcke, wie worker für den zugrunde liegenden Scheduler verfügbar sind.

## <a name="syntax"></a>Syntax

```cpp
class static_partitioner;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[static_partitioner](#ctor)|Erstellt ein `static_partitioner`-Objekt.|
|[~ static_partitioner-Dekonstruktor](#dtor)|Zerstört ein `static_partitioner` -Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`static_partitioner`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppl. h

**Namespace:** Parallelität

## <a name="dtor"></a>~ static_partitioner

Zerstört ein `static_partitioner` -Objekt.

```cpp
~static_partitioner();
```

## <a name="ctor"></a>static_partitioner

Erstellt ein `static_partitioner`-Objekt.

```cpp
static_partitioner();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
