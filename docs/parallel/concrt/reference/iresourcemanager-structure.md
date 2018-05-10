---
title: IResourceManager-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd87a71c8f5d41e38f6a1b18be96a7bab8f3bb8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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
|[IResourceManager::CreateNodeTopology](#createnodetopology)|Vorhanden, nur im Debugbuild der Laufzeit erstellt, diese Methode ist ein Test-Hook entwickelt, um das Testen des Ressourcen-Managers auf unterschiedliche Hardware Topologien, ohne tatsächliche Hardware entsprechen die Konfiguration zu vereinfachen. Mit der retailbuilds der Laufzeit gibt diese Methode zurück, ohne eine Aktion auszuführen.|  
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Gibt die Anzahl der verfügbaren Knoten zum Ressourcen-Manager zurück.|  
|[IResourceManager::GetFirstNode](#getfirstnode)|Gibt den ersten Knoten in der Reihenfolge zurück, gemäß der Ressourcen-Manager.|  
|[IResourceManager::Reference](#reference)|Inkrementiert den Verweiszähler für den Ressourcen-Manager-Instanz.|  
|[IResourceManager::RegisterScheduler](#registerscheduler)|Registriert einen Planer mit dem Ressourcen-Manager. Sobald der Planer registriert wurde, sollte die Kommunikation mit dem Ressourcen-Manager mit Hilfe der `ISchedulerProxy` Schnittstelle, die zurückgegeben wird.|  
|[IResourceManager::Release](#release)|Dekrementiert den Verweiszähler für den Ressourcen-Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweiszähler ist `0`.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [CreateResourceManager](concurrency-namespace-functions.md) Funktion, um eine Schnittstelle auf die Singletoninstanz des Ressourcen-Manager erhalten. Die Methode inkrementiert die Ressourcen-Manager ein, und rufen Sie die [IResourceManager:: Release](#release) Methode, um den Verweis freizugeben, wenn Sie mit dem Ressourcen-Manager sind. In der Regel wird jedes Zeitplanungsmodul, die Sie erstellen rufen Sie diese Methode während der Erstellung des, und lassen den Verweis auf die Ressourcen-Manager, nachdem es heruntergefahren.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IResourceManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="createnodetopology"></a>  IResourceManager:: CreateNodeTopology-Methode  
 Vorhanden, nur im Debugbuild der Laufzeit erstellt, diese Methode ist ein Test-Hook entwickelt, um das Testen des Ressourcen-Managers auf unterschiedliche Hardware Topologien, ohne tatsächliche Hardware entsprechen die Konfiguration zu vereinfachen. Mit der retailbuilds der Laufzeit gibt diese Methode zurück, ohne eine Aktion auszuführen.  
  
```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `nodeCount`  
 Die Anzahl der simulierten Prozessorpaketen.  
  
 `pCoreCount`  
 Ein Array, das die Anzahl der Kerne auf jedem Knoten angibt.  
  
 `pNodeDistance`  
 Eine Matrix, die die Knoten-Abstand zwischen zwei beliebigen Knoten angeben. Dieser Parameter kann den Wert aufweisen `NULL`.  
  
 `pProcessorGroups`  
 Ein Array, der angibt, die Prozessorgruppen jeder Knoten gehört.  
  
### <a name="remarks"></a>Hinweise  
 [Invalid_argument](../../../standard-library/invalid-argument-class.md) wird ausgelöst, wenn der Parameter `nodeCount` hat den Wert `0` übergeben wurde, oder wenn der Parameter `pCoreCount` hat den Wert `NULL`.  
  
 [Invalid_operation](invalid-operation-class.md) wird ausgelöst, wenn diese Methode aufgerufen wird, während andere Planer im Prozess vorhanden sind.  
  
##  <a name="getavailablenodecount"></a>  IResourceManager:: Getavailablenodecount-Methode  
 Gibt die Anzahl der verfügbaren Knoten zum Ressourcen-Manager zurück.  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Knoten, um die Ressourcen-Manager verfügbar sind.  
  
##  <a name="getfirstnode"></a>  IResourceManager:: Getfirstnode-Methode  
 Gibt den ersten Knoten in der Reihenfolge zurück, gemäß der Ressourcen-Manager.  
  
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
 Inkrementiert den Verweiszähler für den Ressourcen-Manager-Instanz.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der resultierende Verweiszähler.  
  
##  <a name="registerscheduler"></a>  IResourceManager:: RegisterScheduler-Methode  
 Registriert einen Planer mit dem Ressourcen-Manager. Sobald der Planer registriert wurde, sollte die Kommunikation mit dem Ressourcen-Manager mit Hilfe der `ISchedulerProxy` Schnittstelle, die zurückgegeben wird.  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pScheduler`  
 Ein `IScheduler` Schnittstelle zum Planer, der registriert werden.  
  
 `version`  
 Die Version der Kommunikationsschnittstelle ist das Zeitplanungsmodul verwenden, mit der Ressourcen-Manager kommunizieren. Verwenden Sie eine Version ermöglicht der Ressourcen-Manager die Kommunikationsschnittstelle weiterentwickelt wird, während gleichzeitig die Zeitplanungsmodule, um Zugriff auf ältere Funktionen zu erhalten. Planer, die Ressourcen-Manager-Funktionen in Visual Studio 2010 verwenden möchten, sollten die Version verwenden `CONCRT_RM_VERSION_1`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `ISchedulerProxy` Schnittstelle der Ressourcen-Manager hat den Planer zugeordnet. Der Planer sollten diese Schnittstelle verwenden, um mit dem Ressourcen-Manager an diesem Punkt auf kommunizieren zu können.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um das Initiieren der Kommunikation mit dem Ressourcen-Manager. Ordnet die Methode die `IScheduler` Schnittstelle für den Planer mit einer `ISchedulerProxy` Schnittstelle und Hände gelangen sie zurück. Sie können die zurückgegebene Schnittstelle Ausführungsressourcen, die für die Verwendung durch den Planer anfordern oder Threads mit der Ressourcen-Manager zu abonnieren. Der Ressourcen-Manager verwendet Richtlinienelemente der Planerrichtlinie zurückgegebenes der [GetPolicy](ischeduler-structure.md#getpolicy) Methode, um zu bestimmen, welche Art von Threads im Zeitplanungsmodul auszuführende Arbeit benötigen. Wenn Ihre `SchedulerKind` Richtlinienschlüssel hat den Wert `UmsThreadDefault` und der Wert wird aus der Richtlinie als der Wert gelesen `UmsThreadDefault`, `IScheduler` Schnittstelle, die an die Methode übergeben werden muss eine `IUMSScheduler` Schnittstelle.  
  
 Löst die Methode eine `invalid_argument` Ausnahme wenn der Parameter `pScheduler` hat den Wert `NULL` oder, wenn der Parameter `version` ist keine gültige Version für die Kommunikationsschnittstelle.  
  
##  <a name="release"></a>  IResourceManager:: Release-Methode  
 Dekrementiert den Verweiszähler für den Ressourcen-Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweiszähler ist `0`.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der resultierende Verweiszähler.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ISchedulerProxy-Struktur](ischedulerproxy-structure.md)   
 [IScheduler-Struktur](ischeduler-structure.md)
