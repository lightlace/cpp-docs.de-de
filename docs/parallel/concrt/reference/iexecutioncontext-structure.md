---
title: IExecutionContext-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
dev_langs:
- C++
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
caps.latest.revision: 18
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 4c4301d7afe46249d6d67ab2a6ec0a9fc2c7935e
ms.lasthandoff: 03/17/2017

---
# <a name="iexecutioncontext-structure"></a>IExecutionContext-Struktur
Eine Schnittstelle zu einem Ausführungskontext, der auf einem angegebenen virtuellen Prozessor ausgeführt werden kann und einen gemeinsamen Kontextwechsel zulässt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IExecutionContext:: Dispatch](#dispatch)|Die Methode, die aufgerufen wird, wenn ein Threadproxy anfängt, einen bestimmten Ausführungskontext ausgeführt. Dies sollte die wichtigsten Worker-Routine für den Planer sein.|  
|[IExecutionContext:: GetID](#getid)|Gibt einen eindeutigen Bezeichner für den Ausführungskontext zurück.|  
|[IExecutionContext:: GetProxy](#getproxy)|Gibt eine Schnittstelle zum Threadproxy, der diesem Kontext ausgeführt wird.|  
|[IExecutionContext:: GetScheduler](#getscheduler)|Gibt eine Schnittstelle für den Planer dieser Ausführungskontext gehört.|  
|[IExecutionContext:: SetProxy](#setproxy)|Ordnet einen Threadproxy Ausführungskontexts. Der zugeordnete Threadproxy ruft diese Methode direkt vor dem Beginn des Kontexts ausgeführt `Dispatch` Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten Planer, das mit der Concurrency Runtime-Ressourcen-Manager kommuniziert implementieren, müssen Sie implementieren die `IExecutionContext` Schnittstelle. Der Ressourcen-Manager erstellten Threads führen arbeiten für den Planer durch Ausführen der `IExecutionContext::Dispatch` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IExecutionContext`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dispatch"></a>IExecutionContext:: Dispatch-Methode  
 Die Methode, die aufgerufen wird, wenn ein Threadproxy anfängt, einen bestimmten Ausführungskontext ausgeführt. Dies sollte die wichtigsten Worker-Routine für den Planer sein.  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pDispatchState`  
 Ein Zeiger auf den Status, unter dem dieser Ausführungskontext weitergeleitet wird. Weitere Informationen zum Status Dispatch, finden Sie unter [DispatchState](dispatchstate-structure.md).  
  
##  <a name="getid"></a>IExecutionContext:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den Ausführungskontext zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine eindeutige ganzzahlige Bezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die Methode `GetExecutionContextId` einen eindeutigen Bezeichner für das Objekt abrufen, implementiert die `IExecutionContext` -Schnittstelle, bevor Sie die Schnittstelle als Parameter für Methoden verwenden der Ressourcen-Manager angegeben. Ihnen wird erwartet, den gleichen Bezeichner zurückzugeben bei der `GetId` -Funktion aufgerufen.  
  
 Ein Bezeichner, der aus einer anderen Quelle erhalten konnte nicht definiertem Verhalten führen.  
  
##  <a name="getproxy"></a>IExecutionContext:: GetProxy-Methode  
 Gibt eine Schnittstelle zum Threadproxy, der diesem Kontext ausgeführt wird.  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `IThreadProxy`-Schnittstelle. Wenn der Threadproxy des Ausführungskontexts nicht mit einem Aufruf von initialisiert wurde `SetProxy`, die Funktion zurück, `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager ruft die `SetProxy` Methode für einen Ausführungskontext mit eine `IThreadProxy` Schnittstelle als Parameter vor dem Eingeben der `Dispatch` Methode auf die im Kontext. Ihnen wird erwartet, dieses Argument zu speichern und bei Aufrufen von zurückgeben `GetProxy()`.  
  
##  <a name="getscheduler"></a>IExecutionContext:: GetScheduler-Methode  
 Gibt eine Schnittstelle für den Planer dieser Ausführungskontext gehört.  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `IScheduler`-Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Es ist erforderlich, den Ausführungskontext mit einer gültigen initialisieren `IScheduler` Schnittstelle vor seiner als Parameter für Methoden Verwendung vom Ressourcen-Manager angegeben.  
  
##  <a name="setproxy"></a>IExecutionContext:: SetProxy-Methode  
 Ordnet einen Threadproxy Ausführungskontexts. Der zugeordnete Threadproxy ruft diese Methode direkt vor dem Beginn des Kontexts ausgeführt `Dispatch` Methode.  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pThreadProxy`  
 Eine Schnittstelle zum Threadproxy, der geben die `Dispatch` -Methode in diesem Ausführungskontext.  
  
### <a name="remarks"></a>Hinweise  
 Ihnen wird erwartet, speichern Sie den Parameter `pThreadProxy` und gibt es bei einem Aufruf der `GetProxy` Methode. Der Ressourcen-Manager garantiert, dass der Ausführungskontext zugeordnete Threadproxy nicht geändert wird, während der Ausführung des Threadproxys den `Dispatch` Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IThreadProxy-Struktur](ithreadproxy-structure.md)

