---
title: IExecutionContext-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c194dc7ecd4af0092dd304b17a8230cda6a8598
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692898"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext-Struktur
Eine Schnittstelle zu einem Ausführungskontext, der auf einem angegebenen virtuellen Prozessor ausgeführt werden kann und einen gemeinsamen Kontextwechsel zulässt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IExecutionContext::Dispatch](#dispatch)|Die Methode, die aufgerufen wird, wenn ein Threadproxy startet die Ausführung eines bestimmten Ausführungskontexts. Dies sollte die Haupt-Worker-Routine, für den Planer sein.|  
|[IExecutionContext::GetId](#getid)|Gibt einen eindeutigen Bezeichner für den Ausführungskontext zurück.|  
|[IExecutionContext::GetProxy](#getproxy)|Gibt eine Schnittstelle zu den Threadproxy, der diesem Kontext ausgeführt wird.|  
|[IExecutionContext::GetScheduler](#getscheduler)|Gibt eine Schnittstelle auf den Planer dieser Ausführungskontext gehört.|  
|[IExecutionContext::SetProxy](#setproxy)|Ordnet einen Threadproxy dieser Ausführungskontext. Der zugeordnete Threadproxy ruft diese Methode auf, unmittelbar vor dem Beginn des Kontexts ausgeführt `Dispatch` Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten Planer, das mit der Concurrency Runtime-Ressourcen-Manager kommuniziert implementieren, müssen Sie zum Implementieren der `IExecutionContext` Schnittstelle. Die Threads vom Ressourcen-Manager erstellt arbeiten für den Planer ausführen, durch das Ausführen der `IExecutionContext::Dispatch` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IExecutionContext`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dispatch"></a>  IExecutionContext:: Dispatch-Methode  
 Die Methode, die aufgerufen wird, wenn ein Threadproxy startet die Ausführung eines bestimmten Ausführungskontexts. Dies sollte die Haupt-Worker-Routine, für den Planer sein.  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pDispatchState`  
 Ein Zeiger auf den Zustand, unter dem dieser Ausführungskontext weitergeleitet wird. Weitere Informationen zum Status der Verteilung, finden Sie unter [DispatchState](dispatchstate-structure.md).  
  
##  <a name="getid"></a>  IExecutionContext:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den Ausführungskontext zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine eindeutige ganzzahlige Bezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die Methode `GetExecutionContextId` einen eindeutigen Bezeichner für das Objekt abrufen, implementiert die `IExecutionContext` Schnittstelle, die vor der Verwendung von der Schnittstelle als Parameter für Methoden angegeben, der Ressourcen-Manager. Ihnen wird erwartet, den gleichen Bezeichner zurückzugeben bei der `GetId` Funktion aufgerufen wird.  
  
 Ein Bezeichner, der aus einer anderen Quelle abgerufen kann zu nicht definiertem Verhalten führen.  
  
##  <a name="getproxy"></a>  IExecutionContext:: GetProxy-Methode  
 Gibt eine Schnittstelle zu den Threadproxy, der diesem Kontext ausgeführt wird.  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `IThreadProxy`-Schnittstelle. Wenn der Ausführungskontext des Threadproxys wurde nicht mit einem Aufruf von initialisiert `SetProxy`, muss die Funktion zurückgeben `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager aufgerufen wird die `SetProxy` -Methode für einen Ausführungskontext mit ein `IThreadProxy` Schnittstelle als Parameter vor dem Eintreten in die `Dispatch` Methode auf die auf dem Kontext. Ihnen wird erwartet, dieses Argument zu speichern und bei Aufrufen zurückgegeben `GetProxy()`.  
  
##  <a name="getscheduler"></a>  IExecutionContext:: GetScheduler-Methode  
 Gibt eine Schnittstelle auf den Planer dieser Ausführungskontext gehört.  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `IScheduler`-Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Sie sind erforderlich, um den Ausführungskontext mit einer gültigen zu initialisieren `IScheduler` Schnittstelle vor der Verwendung als Parameter für Methoden angegeben, der Ressourcen-Manager.  
  
##  <a name="setproxy"></a>  IExecutionContext:: SetProxy-Methode  
 Ordnet einen Threadproxy dieser Ausführungskontext. Der zugeordnete Threadproxy ruft diese Methode auf, unmittelbar vor dem Beginn des Kontexts ausgeführt `Dispatch` Methode.  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pThreadProxy`  
 Eine Schnittstelle zu den Threadproxy, der geben die `Dispatch` Methode in diesem Ausführungskontext.  
  
### <a name="remarks"></a>Hinweise  
 Sie werden zum Speichern des Parameters erwartet `pThreadProxy` und bei einem Aufruf von Zurückgeben der `GetProxy` Methode. Der Ressourcen-Manager wird sichergestellt, dass der Ausführungskontext zugeordnete Threadproxy nicht ändern wird, während der Ausführung des Threadproxys die `Dispatch` Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IThreadProxy-Struktur](ithreadproxy-structure.md)
