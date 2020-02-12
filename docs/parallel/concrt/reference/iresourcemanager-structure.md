---
title: IResourceManager-Struktur
ms.date: 03/27/2019
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
ms.openlocfilehash: 7ce5b07f5eb4272db1b00b7f0105b790ddbb28fe
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142983"
---
# <a name="iresourcemanager-structure"></a>IResourceManager-Struktur

Eine Schnittstelle zum Ressourcen-Manager der Concurrency Runtime. Dies ist die Schnittstelle, über die Planer mit dem Ressourcen-Manager kommunizieren.

## <a name="syntax"></a>Syntax

```cpp
struct IResourceManager;
```

## <a name="members"></a>Members

### <a name="public-enumerations"></a>Öffentliche Enumerationen

|Name|BESCHREIBUNG|
|----------|-----------------|
|[IResourceManager:: OSVersion](#osversion)|Ein enumerierter Typ, der die Betriebssystemversion darstellt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[IResourceManager:: featenodetopology](#createnodetopology)|Diese Methode ist nur in Debugbuilds der Laufzeit vorhanden. diese Methode ist ein testhook, der das Testen der Ressourcen-Manager auf verschiedene hardwaretopologien vereinfacht, ohne dass die tatsächliche Hardware mit der Konfiguration übereinstimmt. Bei Einzelhandels Builds der Laufzeit gibt diese Methode zurück, ohne dass eine Aktion ausgeführt wird.|
|[IResourceManager:: getavailablenodecount](#getavailablenodecount)|Gibt die Anzahl der Knoten zurück, die für die Ressourcen-Manager verfügbar sind.|
|[IResourceManager:: getfirstnode](#getfirstnode)|Gibt den ersten Knoten in der Aufzählungs Reihenfolge zurück, wie vom Ressourcen-Manager definiert.|
|[IResourceManager:: Reference](#reference)|Inkremente den Verweis Zähler für die Ressourcen-Manager Instanz.|
|[IResourceManager:: RegisterScheduler](#registerscheduler)|Registriert einen Planer bei der Ressourcen-Manager. Sobald der Planer registriert ist, sollte er mit dem Ressourcen-Manager über die zurückgegebene `ISchedulerProxy` Schnittstelle kommunizieren.|
|[IResourceManager:: Release](#release)|Dekremente den Verweis Zähler für die Ressourcen-Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweis Zähler auf `0`wechselt.|

## <a name="remarks"></a>Bemerkungen

Verwenden Sie die Funktion " [feateresourcemanager](concurrency-namespace-functions.md) ", um eine Schnittstelle für die Singleton-Ressourcen-Manager Instanz zu erhalten. Die-Methode erhöht den Verweis Zähler für die Ressourcen-Manager, und Sie sollten die [IResourceManager:: Release](#release) -Methode aufrufen, um den Verweis freizugeben, wenn Sie mit Ressourcen-Manager abgeschlossen sind. In der Regel ruft jeder erstellte Scheduler diese Methode während der Erstellung auf und gibt den Verweis auf die Ressourcen-Manager nach dem Herunterladen frei.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IResourceManager`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="createnodetopology"></a>IResourceManager:: featenodetopology-Methode

Diese Methode ist nur in Debugbuilds der Laufzeit vorhanden. diese Methode ist ein testhook, der das Testen der Ressourcen-Manager auf verschiedene hardwaretopologien vereinfacht, ohne dass die tatsächliche Hardware mit der Konfiguration übereinstimmt. Bei Einzelhandels Builds der Laufzeit gibt diese Methode zurück, ohne dass eine Aktion ausgeführt wird.

```cpp
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Parameter

*nodeCount*<br/>
Die Anzahl der zu simulierenden Prozessor Knoten.

*pcorecount*<br/>
Ein Array, das die Anzahl der Kerne auf jedem Knoten angibt.

*pnoabdistance*<br/>
Eine Matrix, die den Knoten Abstand zwischen zwei beliebigen Knoten angibt. Dieser Parameter kann den Wert `NULL`haben.

*pprocessorgroups*<br/>
Ein Array, das die Prozessor Gruppe angibt, zu der jeder Knoten gehört.

### <a name="remarks"></a>Bemerkungen

[Invalid_argument](../../../standard-library/invalid-argument-class.md) wird ausgelöst, wenn der Parameter `nodeCount` den Wert aufweist `0` der übergeben wurde, oder wenn der Parameter `pCoreCount` den Wert `NULL`hat.

[Invalid_operation](invalid-operation-class.md) wird ausgelöst, wenn diese Methode aufgerufen wird, während andere Scheduler im Prozess vorhanden sind.

## <a name="getavailablenodecount"></a>IResourceManager:: getavailablenodecount-Methode

Gibt die Anzahl der Knoten zurück, die für die Ressourcen-Manager verfügbar sind.

```cpp
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der für die Ressourcen-Manager verfügbaren Knoten.

## <a name="getfirstnode"></a>IResourceManager:: getfirstnode-Methode

Gibt den ersten Knoten in der Aufzählungs Reihenfolge zurück, wie vom Ressourcen-Manager definiert.

```cpp
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der erste Knoten in der Aufzählungs Reihenfolge, wie vom Ressourcen-Manager definiert.

## <a name="osversion"></a>IResourceManager:: OSVersion-Enumeration

Ein enumerierter Typ, der die Betriebssystemversion darstellt.

```cpp
enum OSVersion;
```

## <a name="reference"></a>IResourceManager:: Reference-Methode

Inkremente den Verweis Zähler für die Ressourcen-Manager Instanz.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Rückgabewert

Der resultierende Verweis Zähler.

## <a name="registerscheduler"></a>IResourceManager:: RegisterScheduler-Methode

Registriert einen Planer bei der Ressourcen-Manager. Sobald der Planer registriert ist, sollte er mit dem Ressourcen-Manager über die zurückgegebene `ISchedulerProxy` Schnittstelle kommunizieren.

```cpp
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Parameter

*pscheduler*<br/>
Eine `IScheduler`-Schnittstelle zum zu registrierenden Scheduler.

*version*<br/>
Die Version der Kommunikationsschnittstelle, die der Scheduler für die Kommunikation mit dem Ressourcen-Manager verwendet. Die Verwendung einer Version ermöglicht dem Ressourcen-Manager, die Kommunikationsschnittstelle weiter zu entwickeln und gleichzeitig Zeit Planungs Modulen zu ermöglichen, Zugriff auf ältere Funktionen zu erhalten. Bei Zeit Planungs Modulen, die Ressourcen-Manager Funktionen von Visual Studio 2010 verwenden möchten, sollte die Version `CONCRT_RM_VERSION_1`verwendet werden.

### <a name="return-value"></a>Rückgabewert

Die `ISchedulerProxy`-Schnittstelle, die der Ressourcen-Manager Ihrem Scheduler zugeordnet hat. Ihr Scheduler sollte diese Schnittstelle für die Kommunikation mit Ressourcen-Manager ab diesem Zeitpunkt verwenden.

### <a name="remarks"></a>Bemerkungen

Verwenden Sie diese Methode, um die Kommunikation mit dem Ressourcen-Manager zu initiieren. Die-Methode ordnet die `IScheduler`-Schnittstelle für Ihren Scheduler einer `ISchedulerProxy` Schnittstelle zu und übergibt sie an Sie zurück. Sie können die zurückgegebene Schnittstelle verwenden, um Ausführungs Ressourcen für die Verwendung durch den Scheduler anzufordern, oder um Threads mit dem Ressourcen-Manager zu abonnieren. Der Ressourcen-Manager verwendet Richtlinien Elemente aus der von der [IScheduler:: GetPolicy](ischeduler-structure.md#getpolicy) -Methode zurückgegebenen Scheduler-Richtlinie, um zu bestimmen, welche Art von Threads der Planer zum Ausführen von Aufgaben benötigt. Wenn Ihr `SchedulerKind` Richtlinien Schlüssel den Wert `UmsThreadDefault` hat und der Wert aus der Richtlinie zurückgelesen wird, wenn der Wert `UmsThreadDefault`, muss die an die Methode weiter gegebene `IScheduler` Schnittstelle eine `IUMSScheduler` Schnittstelle sein.

Die-Methode löst eine `invalid_argument` Ausnahme aus, wenn der-Parameter `pScheduler` den Wert `NULL` hat, oder wenn der-Parameter `version` keine gültige Version für die Kommunikationsschnittstelle ist.

## <a name="release"></a>IResourceManager:: Release-Methode

Dekremente den Verweis Zähler für die Ressourcen-Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweis Zähler auf `0`wechselt.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Rückgabewert

Der resultierende Verweis Zähler.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[ISchedulerProxy-Struktur](ischedulerproxy-structure.md)<br/>
[IScheduler-Struktur](ischeduler-structure.md)
