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
ms.openlocfilehash: a0d06326b2ecbf3c427ae24b45751f7053778a0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500892"
---
# <a name="staticpartitioner-class"></a>static_partitioner-Klasse

Die `static_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in so viele Blöcke unterteilt, wie Worker für den zugrunde liegenden Planer verfügbar sind.

## <a name="syntax"></a>Syntax

```
class static_partitioner;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[static_partitioner](#ctor)|Erstellt ein `static_partitioner`-Objekt.|
|[~ Static_partitioner-Destruktor](#dtor)|Zerstört ein `static_partitioner`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`static_partitioner`

## <a name="requirements"></a>Anforderungen

**Header:** ppl.h

**Namespace:** Parallelität

##  <a name="dtor"></a> ~static_partitioner

Zerstört ein `static_partitioner`-Objekt.

```
~static_partitioner();
```

##  <a name="ctor"></a> static_partitioner

Erstellt ein `static_partitioner`-Objekt.

```
static_partitioner();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
