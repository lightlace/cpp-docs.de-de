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
ms.openlocfilehash: f3c5792a13d9e63a05ce6710dea77828f2510f0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522446"
---
# <a name="simplepartitioner-class"></a>simple_partitioner-Klasse

Die `simple_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in Blöcke unterteilt, sodass jeder Block mindestens die von der Segmentgröße angegebene Anzahl von Iterationen enthält.

## <a name="syntax"></a>Syntax

```
class simple_partitioner;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[simple_partitioner](#ctor)|Erstellt ein `simple_partitioner`-Objekt.|
|[~ Simple_partitioner-Destruktor](#dtor)|Zerstört ein `simple_partitioner`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`simple_partitioner`

## <a name="requirements"></a>Anforderungen

**Header:** ppl.h

**Namespace:** Parallelität

##  <a name="dtor"></a> ~simple_partitioner

Zerstört ein `simple_partitioner`-Objekt.

```
~simple_partitioner();
```

##  <a name="ctor"></a> simple_partitioner

Erstellt ein `simple_partitioner`-Objekt.

```
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Parameter

*_Chunk_size*<br/>
Die erforderliche Mindestpartitionsgröße angezeigt.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
