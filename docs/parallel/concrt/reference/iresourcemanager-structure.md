---
title: IResourceManager-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IResourceManager
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: fb523127f60c4e8cd45b2525749b536ad55849b0
ms.lasthandoff: 02/24/2017

---
# <a name="iresourcemanager-structure"></a>IResourceManager-Struktur
Eine Schnittstelle zum Ressourcen-Manager der Concurrency Runtime. Dies ist die Schnittstelle, über die Planer mit dem Ressourcen-Manager kommunizieren.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IResourceManager;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-enumerations"></a>Öffentliche Enumerationen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IResourceManager:: OSVersion-Enumeration](#osversion)|Ein enumerierter Typ, der die Betriebssystemversion darstellt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IResourceManager:: CreateNodeTopology-Methode](#createnodetopology)|Vorhanden, nur in der Laufzeit erstellt, diese Methode ist ein Testhook entwickelt, um das Testen des Ressourcen-Managers auf unterschiedliche möglich sind, ohne dass die tatsächliche Hardware, die mit der Konfiguration zu vereinfachen. Mit der Laufzeit Retail-Builds gibt diese Methode zurück, ohne dass eine Aktion ausgeführt.|  
|[IResourceManager:: Getavailablenodecount-Methode](#getavailablenodecount)|Gibt die Anzahl der verfügbaren Knoten, der Ressourcen-Manager zurück.|  
|[IResourceManager:: Getfirstnode-Methode](#getfirstnode)|Gibt den ersten Knoten in der Reihenfolge der Ressourcen-Manager definierte.|  
|[IResourceManager:: Reference-Methode](#reference)|Inkrementiert den Verweiszähler auf der Ressourcen-Manager-Instanz.|  
|[IResourceManager:: RegisterScheduler-Methode](#registerscheduler)|Registriert einen Planer mit dem Ressourcen-Manager. Sobald der Planer registriert wurde, sollte die Kommunikation mit dem Ressourcen-Manager über die `ISchedulerProxy` -Schnittstelle, die zurückgegeben wird.|  
|[IResourceManager:: Release-Methode](#release)|Dekrementiert den Verweiszähler für die Ressourcen-Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweiszähler ist `0`.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [CreateResourceManager](concurrency-namespace-functions.md) Funktion, um eine Schnittstelle für die Singleton-Ressourcen-Manager-Instanz zu erhalten. Die Methode inkrementiert auf dem Ressourcen-Manager ein, und rufen Sie die [IResourceManager:: Release](#release) Methode zum Freigeben des Verweises, wenn Sie mit dem Ressourcen-Manager fertig sind. In der Regel wird jeder Planer, den Sie erstellen diese Methode aufgerufen wird, während der Erstellung, und den Verweis auf den Ressourcen-Manager frei, nachdem es heruntergefahren.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IResourceManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namecreatenodetopologya--iresourcemanagercreatenodetopology-method"></a><a name="createnodetopology"></a>IResourceManager:: CreateNodeTopology-Methode  
 Vorhanden, nur in der Laufzeit erstellt, diese Methode ist ein Testhook entwickelt, um das Testen des Ressourcen-Managers auf unterschiedliche möglich sind, ohne dass die tatsächliche Hardware, die mit der Konfiguration zu vereinfachen. Mit der Laufzeit Retail-Builds gibt diese Methode zurück, ohne dass eine Aktion ausgeführt.  
  
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
 Eine Matrix, die Knoten Abstand zwischen zwei beliebigen Knoten angeben. Dieser Parameter kann den Wert aufweisen `NULL`.  
  
 `pProcessorGroups`  
 Ein Array, das die Prozessorgruppen gibt jeder Knoten gehört.  
  
### <a name="remarks"></a>Hinweise  
 [Invalid_argument](../../../standard-library/invalid-argument-class.md) wird ausgelöst, wenn der Parameter `nodeCount` hat den Wert `0` übergeben wurde, oder wenn der Parameter `pCoreCount` hat den Wert `NULL`.  
  
 [Invalid_operation](invalid-operation-class.md) wird ausgelöst, wenn diese Methode aufgerufen wird, während andere Planer im Prozess vorhanden sind.  
  
##  <a name="a-namegetavailablenodecounta--iresourcemanagergetavailablenodecount-method"></a><a name="getavailablenodecount"></a>IResourceManager:: Getavailablenodecount-Methode  
 Gibt die Anzahl der verfügbaren Knoten, der Ressourcen-Manager zurück.  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Knoten, der Ressourcen-Manager verfügbar.  
  
##  <a name="a-namegetfirstnodea--iresourcemanagergetfirstnode-method"></a><a name="getfirstnode"></a>IResourceManager:: Getfirstnode-Methode  
 Gibt den ersten Knoten in der Reihenfolge der Ressourcen-Manager definierte.  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste Knoten in der Reihenfolge gemäß der Ressourcen-Manager.  
  
##  <a name="a-nameiresourcemanagerosversiona--iresourcemanagerosversion-enumeration"></a><a name="iresourcemanager__osversion"></a>IResourceManager:: OSVersion-Enumeration  
 Ein enumerierter Typ, der die Betriebssystemversion darstellt.  
  
```
enum OSVersion;
```  
  
##  <a name="a-namereferencea--iresourcemanagerreference-method"></a><a name="reference"></a>IResourceManager:: Reference-Methode  
 Inkrementiert den Verweiszähler auf der Ressourcen-Manager-Instanz.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der resultierende Verweiszähler.  
  
##  <a name="a-nameregisterschedulera--iresourcemanagerregisterscheduler-method"></a><a name="registerscheduler"></a>IResourceManager:: RegisterScheduler-Methode  
 Registriert einen Planer mit dem Ressourcen-Manager. Sobald der Planer registriert wurde, sollte die Kommunikation mit dem Ressourcen-Manager über die `ISchedulerProxy` -Schnittstelle, die zurückgegeben wird.  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pScheduler`  
 Eine `IScheduler` Schnittstelle zum Planer, der registriert werden.  
  
 `version`  
 Die Version der Kommunikationsschnittstelle verwendet der Planer mit dem Ressourcen-Manager kommunizieren. Eine Version ermöglicht der Ressourcen-Manager die Kommunikationsschnittstelle entwickeln, während Planer Zugriff auf ältere Funktionen erhalten. Planer, die Ressourcen-Manager-Funktionen in Visual Studio 2010 verwenden möchten, verwenden Sie die Version sollte `CONCRT_RM_VERSION_1`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `ISchedulerProxy` Schnittstelle, die den Ressourcen-Manager dem Planer zugeordnet. Der Planer sollte diese Schnittstelle verwenden, mit dem Ressourcen-Manager an diesem Punkt kommunizieren.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zur Initiierung der Kommunikation mit dem Ressourcen-Manager. Die Methode ordnet die `IScheduler` Schnittstelle für den Planer mit einer `ISchedulerProxy` -Schnittstelle zu und gibt sie zurück. Sie können die zurückgegebene Schnittstelle Ausführungsressourcen für die Verwendung durch den Planer anfordern oder Threads mit dem Ressourcen-Manager abonnieren. Der Ressourcen-Manager verwendet Richtlinienelemente der Planerrichtlinie, die zurückgegeben werden, indem Sie die [GetPolicy](ischeduler-structure.md#getpolicy) Methode, um zu bestimmen, welche Art von Threads den Planer für die Arbeit benötigen. Wenn Ihre `SchedulerKind` -Richtlinienschlüssel auf den Wert `UmsThreadDefault` und der Wert wird aus der Richtlinie als Wert gelesen `UmsThreadDefault`, `IScheduler` an die Methode übergeben werden eine `IUMSScheduler` Schnittstelle.  
  
 Löst die Methode eine `invalid_argument` Ausnahme wenn der Parameter `pScheduler` hat den Wert `NULL` oder, wenn der Parameter `version` ist keine gültige Version für die Kommunikationsschnittstelle.  
  
##  <a name="a-namereleasea--iresourcemanagerrelease-method"></a><a name="release"></a>IResourceManager:: Release-Methode  
 Dekrementiert den Verweiszähler für die Ressourcen-Manager-Instanz. Der Ressourcen-Manager wird zerstört, wenn der Verweiszähler ist `0`.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der resultierende Verweiszähler.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [ISchedulerProxy-Struktur](ischedulerproxy-structure.md)   
 [IScheduler-Struktur](ischeduler-structure.md)

