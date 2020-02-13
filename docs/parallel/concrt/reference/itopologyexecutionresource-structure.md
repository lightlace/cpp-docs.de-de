---
title: ITopologyExecutionResource-Struktur
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: 82193a9b592cded96f3726cbabd6cf646eaa27c8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140068"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource-Struktur

Eine Schnittstelle zu einer vom Ressourcen-Manager definierten Ausführungsressource.

## <a name="syntax"></a>Syntax

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Itopologyexecutionresource:: GetId](#getid)|Gibt den eindeutigen Bezeichner der Ressourcen-Manager für diese Ausführungs Ressource zurück.|
|[Itopologyexecutionresource:: GetNext](#getnext)|Gibt eine Schnittstelle zur nächsten Ausführungs Ressource in der Aufzählungs Reihenfolge zurück.|

## <a name="remarks"></a>Bemerkungen

Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems zu durchlaufen, wie von der Ressourcen-Manager beobachtet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ITopologyExecutionResource`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="getid"></a>Itopologyexecutionresource:: GetId-Methode

Gibt den eindeutigen Bezeichner der Ressourcen-Manager für diese Ausführungs Ressource zurück.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der eindeutige Bezeichner des Ressourcen-Manager für diese Ausführungs Ressource.

## <a name="getnext"></a>Itopologyexecutionresource:: GetNext-Methode

Gibt eine Schnittstelle zur nächsten Ausführungs Ressource in der Aufzählungs Reihenfolge zurück.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Schnittstelle zur nächsten Ausführungs Ressource in der Aufzählungs Reihenfolge. Wenn in der Aufzählungs Reihenfolge des Knotens, zu dem diese Ausführungs Ressource gehört, keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert `NULL`zurück.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
