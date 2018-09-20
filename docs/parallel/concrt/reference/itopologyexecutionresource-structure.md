---
title: ITopologyExecutionResource-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60a0097aded73e3e0251d38daf5da71197668d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383791"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource-Struktur

Eine Schnittstelle zu einer vom Ressourcen-Manager definierten Ausführungsressource.

## <a name="syntax"></a>Syntax

```
struct ITopologyExecutionResource;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Itopologyexecutionresource:: GetID](#getid)|Gibt zurück, der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.|
|[ITopologyExecutionResource::GetNext](#getnext)|Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge der zurück.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems führen, als vom Ressourcen-Manager überwacht.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ITopologyExecutionResource`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="getid"></a>  Itopologyexecutionresource:: GetID-Methode

Gibt zurück, der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der Resource Manager Eindeutiger Bezeichner für diese Ausführungsressource.

##  <a name="getnext"></a>  Itopologyexecutionresource:: GetNext-Methode

Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge der zurück.

```
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge der. Wenn die Reihenfolge des Knotens, zu dem diese Ausführungsressource gehört, keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert `NULL`.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
