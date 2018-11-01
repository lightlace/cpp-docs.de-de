---
title: Static_partitioner-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de1b63cf24fbc84130302fcbae2cb965e8d00597
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376019"
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
