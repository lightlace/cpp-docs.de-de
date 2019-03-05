---
title: IResourceManager-Struktur
ms.date: 11/04/2016
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
ms.openlocfilehash: 1f8f5992d9ce55100d193196a3c0f94b468ef892
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275267"
---
# <a name="iresourcemanager-structure"></a>IResourceManager-Struktur

Eine Schnittstelle zum Ressourcen-Manager der Concurrency Runtime. Dies ist die Schnittstelle, über die Planer mit dem Ressourcen-Manager kommunizieren.

## <a name="syntax"></a>Syntax

```
struct IResourceManager;
```

## <a name="members"></a>Member

### <a name="public-enumerations"></a>Öffentliche Enumerationen

|Name|Beschreibung|
|----------|-----------------|
|[IResourceManager::OSVersion](#osversion)|Ein enumerierter Typ, der die Betriebssystemversion darstellt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IResourceManager::CreateNodeTopology](#createnodetopology)|Derzeit nur im Debugbuild der Laufzeit erstellt, diese Methode ist ein Test-Hook, erleichtern des Ressourcen-Managers auf unterschiedlichen Hardware-Topologien, ohne tatsächliche Hardware, die übereinstimmende Konfiguration testen soll. Mit der Laufzeit Retail-Builds gibt diese Methode zurück, ohne dass eine Aktion ausgeführt.|
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Gibt die Anzahl der verfügbaren Knoten, der Ressourcen-Manager zurück.|
|[IResourceManager::GetFirstNode](#getfirstnode)|Gibt den ersten Knoten in der Reihenfolge der Enumeration zurück, gemäß der Ressourcen-Manager.|
|[IResourceManager::Reference](#reference)|Inkrementiert den Verweiszähler für die Resource Manager-Instanz.|
|[IResourceManager::RegisterScheduler](#registerscheduler)|Registriert einen Planer mit dem Resource Manager. Sobald der Planer registriert wurde, sollte er mit dem Ressourcen-Manager mit kommunizieren die `ISchedulerProxy` -Schnittstelle, die zurückgegeben wird.|
|[IResourceManager::Release](#release)|Dekrementiert den Verweiszähler für die Resource Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweiszähler ist `0`.|

## <a name="remarks"></a>Hinweise

Verwenden der [CreateResourceManager](concurrency-namespace-functions.md) Funktion, die eine Schnittstelle für die Singletoninstanz des Ressourcen-Manager zu erhalten. Die Methode inkrementiert auf die Ressourcen-Manager einen, und Sie sollten aufrufen, die [IResourceManager:: Release](#release) Methode, um den Verweis freizugeben, wenn Sie mit dem Resource Manager haben. In der Regel wird jedes Zeitplanungsmodul, die Sie erstellen diese Methode aufgerufen wird, während der Erstellung, und den Verweis auf die Ressourcen-Manager frei, nachdem es heruntergefahren wurde.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IResourceManager`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="createnodetopology"></a>  IResourceManager:: CreateNodeTopology-Methode

Derzeit nur im Debugbuild der Laufzeit erstellt, diese Methode ist ein Test-Hook, erleichtern des Ressourcen-Managers auf unterschiedlichen Hardware-Topologien, ohne tatsächliche Hardware, die übereinstimmende Konfiguration testen soll. Mit der Laufzeit Retail-Builds gibt diese Methode zurück, ohne dass eine Aktion ausgeführt.

```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Parameter

*nodeCount*<br/>
Die Anzahl der simulierten Prozessorpaketen.

*pCoreCount*<br/>
Ein Array, der angibt, die Anzahl der Kerne auf jedem Knoten.

*pNodeDistance*<br/>
Eine Matrix, die die Knoten-Abstand zwischen zwei beliebigen Knoten angeben. Dieser Parameter kann den Wert aufweisen `NULL`.

*pProcessorGroups*<br/>
Ein Array, das der Gruppe "Prozessor" gibt an, zu jedem Knoten gehört.

### <a name="remarks"></a>Hinweise

[Invalid_argument](../../../standard-library/invalid-argument-class.md) wird ausgelöst, wenn der Parameter `nodeCount` hat den Wert `0` übergeben wurde, oder wenn der Parameter `pCoreCount` hat den Wert `NULL`.

[Invalid_operation](invalid-operation-class.md) wird ausgelöst, wenn diese Methode aufgerufen wird, während andere Planer des Prozesses vorhanden sind.

##  <a name="getavailablenodecount"></a>  IResourceManager:: Getavailablenodecount-Methode

Gibt die Anzahl der verfügbaren Knoten, der Ressourcen-Manager zurück.

```
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Knoten, der Ressourcen-Manager verfügbar sind.

##  <a name="getfirstnode"></a>  IResourceManager:: Getfirstnode-Methode

Gibt den ersten Knoten in der Reihenfolge der Enumeration zurück, gemäß der Ressourcen-Manager.

```
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der erste Knoten in der Reihenfolge gemäß der Ressourcen-Manager.

##  <a name="iresourcemanager__osversion"></a>  IResourceManager:: OSVersion-Enumeration

Ein enumerierter Typ, der die Betriebssystemversion darstellt.

```
enum OSVersion;
```

##  <a name="reference"></a>  IResourceManager:: Reference-Methode

Inkrementiert den Verweiszähler für die Resource Manager-Instanz.

```
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Rückgabewert

Der resultierende Verweiszähler.

##  <a name="registerscheduler"></a>  IResourceManager:: RegisterScheduler-Methode

Registriert einen Planer mit dem Resource Manager. Sobald der Planer registriert wurde, sollte er mit dem Ressourcen-Manager mit kommunizieren die `ISchedulerProxy` -Schnittstelle, die zurückgegeben wird.

```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Parameter

*pScheduler*<br/>
Ein `IScheduler` Schnittstelle, um den Scheduler so registriert werden.

*version*<br/>
Die Version der Kommunikationsschnittstelle wird der Scheduler für die Kommunikation mit dem Resource Manager verwendet. Mit einer Version ermöglicht der Ressourcen-Manager die Kommunikationsschnittstelle entwickeln, während Zeitplanungsmodule, um Zugriff auf ältere Funktionen zu erhalten. Zeitplanungsmodule, die Ressourcen-Manager-Funktionen in Visual Studio 2010 verwenden möchten, sollten die Version verwenden `CONCRT_RM_VERSION_1`.

### <a name="return-value"></a>Rückgabewert

Die `ISchedulerProxy` Schnittstelle, die den Ressourcen-Manager den Planer zugeordnet ist. Der Planer sollten diese Schnittstelle verwenden, mit dem Resource Manager an diesem Punkt kommunizieren.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um die Kommunikation mit dem Resource Manager initiieren. Die Methode ordnet die `IScheduler` Schnittstelle für den Planer mit einer `ISchedulerProxy` -Schnittstelle und gibt sie zurück, für Sie. Sie können die zurückgegebene Schnittstelle zum Anfordern von Ressourcen für die Verwendung durch den Planer zur Ausführung oder Abonnieren von Threads mit dem Resource Manager verwenden. Der Ressourcen-Manager verwendet die Richtlinienelemente, die von der vom Scheduler-Richtlinie die [GetPolicy](ischeduler-structure.md#getpolicy) Methode, um zu bestimmen, welche Art von Threads den Planer zum Arbeitsaufgaben ausführen müssen. Wenn Ihre `SchedulerKind` Richtlinienschlüssel hat den Wert `UmsThreadDefault` und der Wert wird aus der Richtlinie als der Wert gelesen `UmsThreadDefault`, `IScheduler` Schnittstelle, die an die Methode übergeben werden muss ein `IUMSScheduler` Schnittstelle.

Löst die Methode eine `invalid_argument` Ausnahme wenn der Parameter `pScheduler` hat den Wert `NULL` oder, wenn der Parameter `version` ist keine gültige Version für die Kommunikationsschnittstelle.

##  <a name="release"></a>  IResourceManager:: Release-Methode

Dekrementiert den Verweiszähler für die Resource Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweiszähler ist `0`.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Rückgabewert

Der resultierende Verweiszähler.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[ISchedulerProxy-Struktur](ischedulerproxy-structure.md)<br/>
[IScheduler-Struktur](ischeduler-structure.md)
