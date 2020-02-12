---
title: ITopologyNode-Struktur
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 1b4cb6a856d6da7b8eee7f9cba1ad51e375c024d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140059"
---
# <a name="itopologynode-structure"></a>ITopologyNode-Struktur

Eine Schnittstelle für einen vom Ressourcen-Manager definierten Topologieknoten. Ein Knoten enthält mindestens eine Ausführungsressource.

## <a name="syntax"></a>Syntax

```cpp
struct ITopologyNode;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Itopologynode:: getexecutionresourcecount](#getexecutionresourcecount)|Gibt die Anzahl der Ausführungs Ressourcen zurück, die unter diesem Knoten gruppiert sind.|
|[Itopologynode:: getfirstexecutionresource](#getfirstexecutionresource)|Gibt die erste Ausführungs Ressource zurück, die in der Enumerationsfolge unter diesem Knoten gruppiert ist.|
|[Itopologynode:: GetId](#getid)|Gibt den eindeutigen Bezeichner des Ressourcen-Manager für diesen Knoten zurück.|
|[Itopologynode:: GetNext](#getnext)|Gibt eine Schnittstelle zum nächsten topologieknoten in der Aufzählungs Reihenfolge zurück.|
|[Itopologynode:: getnumanode](#getnumanode)|Gibt die von Windows zugewiesene NUMA-Knotenzahl zurück, zu der dieser Ressource-Manager-Knoten gehört.|

## <a name="remarks"></a>Bemerkungen

Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems zu durchlaufen, wie von der Ressourcen-Manager beobachtet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ITopologyNode`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="getexecutionresourcecount"></a>Itopologynode:: getexecutionresourcecount-Methode

Gibt die Anzahl der Ausführungs Ressourcen zurück, die unter diesem Knoten gruppiert sind.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Ausführungs Ressourcen, die unter diesem Knoten gruppiert sind.

## <a name="getfirstexecutionresource"></a>Itopologynode:: getfirstexecutionresource-Methode

Gibt die erste Ausführungs Ressource zurück, die in der Enumerationsfolge unter diesem Knoten gruppiert ist.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die erste Ausführungs Ressource, die in der Enumerationsfolge unter diesem Knoten gruppiert ist.

## <a name="getid"></a>Itopologynode:: GetId-Methode

Gibt den eindeutigen Bezeichner des Ressourcen-Manager für diesen Knoten zurück.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der eindeutige Bezeichner des Ressourcen-Manager für diesen Knoten.

### <a name="remarks"></a>Bemerkungen

Der Concurrency Runtime stellt Hardwarethreads auf dem System in Gruppen von Prozessor Knoten dar. Knoten werden normalerweise von der Hardware Topologie des Systems abgeleitet. Beispielsweise können alle Prozessoren eines bestimmten Sockets oder eines bestimmten NUMA-Knotens zum gleichen Prozessor Knoten gehören. Der Ressourcen-Manager weist diesen Knoten, beginnend mit `0` bis einschließlich `nodeCount - 1`, eindeutige Bezeichner zu, wobei `nodeCount` die Gesamtzahl der Prozessor Knoten im System darstellt.

Die Anzahl der Knoten kann aus der Funktion " [getprocessornoentcount](concurrency-namespace-functions.md)" abgerufen werden.

## <a name="getnext"></a>Itopologynode:: GetNext-Methode

Gibt eine Schnittstelle zum nächsten topologieknoten in der Aufzählungs Reihenfolge zurück.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Schnittstelle zum nächsten Knoten in der Aufzählungs Reihenfolge. Wenn in der Aufzählungs Reihenfolge der System Topologie keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert `NULL`zurück.

## <a name="getnumanode"></a>Itopologynode:: getnumanode-Methode

Gibt die von Windows zugewiesene NUMA-Knotenzahl zurück, zu der dieser Ressource-Manager-Knoten gehört.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die von Windows zugewiesene NUMA-Knotenzahl, zu der dieser Ressource-Manager-Knoten gehört.

### <a name="remarks"></a>Bemerkungen

Ein Threadproxy, der auf einem virtuellen Prozessorstamm ausgeführt wird, der zu diesem Knoten gehört, verfügt über Affinität zu mindestens der NUMA-Knotenebene für den NUMA-Knoten, der von dieser Methode zurückgegeben wird.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
