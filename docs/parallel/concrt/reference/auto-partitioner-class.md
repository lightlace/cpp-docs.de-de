---
title: auto_partitioner-Klasse
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: 4d1d8f19069412240de8e9d69cdcfb34618f2796
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142866"
---
# <a name="auto_partitioner-class"></a>auto_partitioner-Klasse

Die `auto_partitioner`-Klasse stellt die Standardmethoden `parallel_for`, `parallel_for_each` und `parallel_transform` dar, die verwendet werden, um den Bereich zu partitionieren, den sie durchlaufen. Diese Partitionierungs Methode setzt den Bereichs Diebstahl für den Lastenausgleich und den Abbruch pro iterate ein.

## <a name="syntax"></a>Syntax

```cpp
class auto_partitioner;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[auto_partitioner](#ctor)|Erstellt ein `auto_partitioner`-Objekt.|
|[~ auto_partitioner-Dekonstruktor](#dtor)|Zerstört ein `auto_partitioner` -Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`auto_partitioner`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppl. h

**Namespace:** Parallelität

## <a name="dtor"></a>~ auto_partitioner

Zerstört ein `auto_partitioner` -Objekt.

```cpp
~auto_partitioner();
```

## <a name="ctor"></a>auto_partitioner

Erstellt ein `auto_partitioner`-Objekt.

```cpp
auto_partitioner();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
