---
title: Auto_partitioner-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
dev_langs:
- C++
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2bb62d76733e77c2528a80dfc4e9ef358878895
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425401"
---
# <a name="autopartitioner-class"></a>auto_partitioner-Klasse

Die `auto_partitioner`-Klasse stellt die Standardmethoden `parallel_for`, `parallel_for_each` und `parallel_transform` dar, die verwendet werden, um den Bereich zu partitionieren, den sie durchlaufen. Diese Partitionierungsmethode verwendet Bereichsstealing zum Lastenausgleich sowie Abbruch pro Durchlauf.

## <a name="syntax"></a>Syntax

```
class auto_partitioner;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[auto_partitioner](#ctor)|Erstellt ein `auto_partitioner`-Objekt.|
|[~ Auto_partitioner-Destruktor](#dtor)|Zerstört ein `auto_partitioner`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`auto_partitioner`

## <a name="requirements"></a>Anforderungen

**Header:** ppl.h

**Namespace:** Parallelität

##  <a name="dtor"></a> ~ Auto_partitioner

Zerstört ein `auto_partitioner`-Objekt.

```
~auto_partitioner();
```

##  <a name="ctor"></a> auto_partitioner

Erstellt ein `auto_partitioner`-Objekt.

```
auto_partitioner();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
