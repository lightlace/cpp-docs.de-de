---
title: CWorkerThread Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be7a000e48cb044a67f7eee120206f46ecaef2ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cworkerthread-class"></a>CWorkerThread-Klasse
Diese Klasse wird ein Arbeitsthread erstellt oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernel-Objekt-Handles und führt eine angegebene Client-Funktion aus, wenn Sie einen der Ziehpunkte signalisiert wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>Parameter  
 `ThreadTraits`  
 Die Klasse, die die Thread-Erstellung-Funktion, wie z. B. Bereitstellung [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) oder [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## <a name="members"></a>Member  
  
### <a name="protected-structures"></a>Geschützte Strukturen  
  
|name|Beschreibung|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|Der Konstruktor für den Arbeitsthread.|  
|[CWorkerThread:: ~ CWorkerThread](#dtor)|Der Destruktor für den Arbeitsthread.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|Rufen Sie diese Methode, um die Liste von Arbeitsthreads verwaltet ein Wait Handle des Objekts hinzuzufügen.|  
|[CWorkerThread::AddTimer](#addtimer)|Rufen Sie diese Methode, um einen periodischen Lage Timer, der durch den Arbeitsthread verwalteten Liste hinzuzufügen.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Rufen Sie diese Methode, um das Threadhandle des Arbeitsthreads zu erhalten.|  
|[CWorkerThread::GetThreadId](#getthreadid)|Rufen Sie diese Methode zum Abrufen der Thread-ID des Arbeitsthreads.|  
|[CWorkerThread::Initialize](#initialize)|Rufen Sie diese Methode, um den Arbeitsthread zu initialisieren.|  
|[CWorkerThread::RemoveHandle](#removehandle)|Rufen Sie diese Methode, um ein Handle aus der Liste der Lage, Objekte zu entfernen.|  
|[CWorkerThread::Shutdown](#shutdown)|Rufen Sie diese Methode, um den Arbeitsthread zu schließen.|  
  
## <a name="remarks"></a>Hinweise  
  
### <a name="to-use-cworkerthread"></a>CWorkerThread verwenden  
  
1.  Erstellen Sie eine Instanz dieser Klasse.  
  
2.  Rufen Sie [CWorkerThread::Initialize](#initialize).  
  
3.  Rufen Sie [CWorkerThread::AddHandle](#addhandle) mit dem Handle des Kernel-Objekt und einen Zeiger auf eine Implementierung der [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     - ODER  
  
     Rufen Sie [CWorkerThread::AddTimer](#addtimer) mit einem Zeiger auf eine Implementierung der [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  Implementieren [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Maßnahmen zu ergreifen, wenn das Handle oder der Timer signalisiert wird.  
  
5.  Rufen Sie zum Entfernen eines Objekts aus der Liste der Objekte Lage [CWorkerThread::RemoveHandle](#removehandle).  
  
6.  Um den Thread zu beenden, rufen [CWorkerThread::Shutdown](#shutdown).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="addhandle"></a>CWorkerThread::AddHandle  
 Rufen Sie diese Methode, um die Liste von Arbeitsthreads verwaltet ein Wait Handle des Objekts hinzuzufügen.  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Das Handle für ein Objekt mit wartemöglichkeit.  
  
 `pClient`  
 Der Zeiger auf die [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) Schnittstelle für das Objekt aufgerufen werden, wenn das Handle signalisiert wird.  
  
 `dwParam`  
 Der Parameter zu übergebenden [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Wenn das Handle signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) aufgerufen wird, über `pClient` Wenn das Handle `hObject`, signalisiert wird.  
  
##  <a name="addtimer"></a>CWorkerThread::AddTimer  
 Rufen Sie diese Methode, um einen periodischen Lage Timer, der durch den Arbeitsthread verwalteten Liste hinzuzufügen.  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwInterval*  
 Gibt den Zeitraum des Zeitgebers in Millisekunden an.  
  
 `pClient`  
 Der Zeiger auf die [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) Schnittstelle für das Objekt aufgerufen werden, wenn das Handle signalisiert wird.  
  
 `dwParam`  
 Der Parameter zu übergebenden [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Wenn das Handle signalisiert wird.  
  
 `phTimer`  
 [out] Die Adresse der HANDLE-Variablen, die bei Erfolg das Handle für den neu erstellten Zeitgeber empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) aufgerufen wird, über `pClient` Wenn der Zeitgeber signalisiert wird.  
  
 Übergeben Sie das Timer-Handle aus `phTimer` auf [CWorkerThread::RemoveHandle](#removehandle) um den Zeitgeber zu schließen.  
  
##  <a name="cworkerthread"></a>CWorkerThread::CWorkerThread  
 Der Konstruktor.  
  
```
CWorkerThread() throw();
```  
  
##  <a name="dtor"></a>CWorkerThread:: ~ CWorkerThread  
 Der Destruktor.  
  
```
~CWorkerThread() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CWorkerThread::Shutdown](#shutdown).  
  
##  <a name="getthreadhandle"></a>CWorkerThread::GetThreadHandle  
 Rufen Sie diese Methode, um das Threadhandle des Arbeitsthreads zu erhalten.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Thread wurde nicht initialisiert das Threadhandle oder NULL zurückgegeben werden soll.  
  
##  <a name="getthreadid"></a>CWorkerThread::GetThreadId  
 Rufen Sie diese Methode zum Abrufen der Thread-ID des Arbeitsthreads.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Thread wurde nicht initialisiert die Thread-ID oder NULL zurückgegeben werden soll.  
  
##  <a name="initialize"></a>CWorkerThread::Initialize  
 Rufen Sie diese Methode, um den Arbeitsthread zu initialisieren.  
  
```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pThread`  
 Ein Arbeitsthread.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte aufgerufen werden, um das Objekt zu initialisieren, nach der Erstellung oder nach einem Aufruf von [CWorkerThread::Shutdown](#shutdown).  
  
 Haben Sie zwei oder mehr `CWorkerThread` Objekte im gleichen Arbeitsthread verwenden, initialisieren Sie eine von ihnen ohne übergeben, die keine Argumente übergeben dann einen Zeiger auf das Objekt an den `Initialize` von den anderen Methoden. Initialisiert unter Verwendung des Zeigers Objekte sollten heruntergefahren werden, vor dem Objekt verwendet, um sie zu initialisieren.  
  
 Finden Sie unter [CWorkerThread::Shutdown](#shutdown) Informationen wie diese Methode verhaltensänderungen bei der Initialisierung mithilfe eines Zeigers auf ein vorhandenes Objekt.  
  
##  <a name="removehandle"></a>CWorkerThread::RemoveHandle  
 Rufen Sie diese Methode, um ein Handle aus der Liste der Lage, Objekte zu entfernen.  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Das Handle zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Handle entfernt wird [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) wird aufgerufen werden, auf das zugeordnete Objekt, das übergebene [AddHandle](#addhandle). Wenn dieser Aufruf fehlschlägt, `CWorkerThread` aufrufen, wird die Windows [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) Funktion auf das Handle.  
  
##  <a name="shutdown"></a>CWorkerThread::Shutdown  
 Rufen Sie diese Methode, um den Arbeitsthread zu schließen.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwWait`  
 Die Zeit in Millisekunden zu warten, bis der Arbeitsthread beendet werden soll. ATL_WORKER_THREAD_WAIT Standardwert ist 10 Sekunden. Bei Bedarf können Sie einen eigenen Wert für dieses Symbol vor dem Einfügen von atlutil.h definieren. 
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, auf Erfolg oder einen HRESULT-Fehler bei einem Fehler, z. B. wenn der Timeoutwert `dwWait`, überschritten wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt wiederverwenden möchten, rufen Sie [CWorkerThread::Initialize](#initialize) nach dem Aufrufen dieser Methode.  
  
 Beachten Sie, dass der Aufruf **Herunterfahren** für ein Objekt mit einem Zeiger auf eine andere initialisiert `CWorkerThread` Objekt hat keine Auswirkung und stets S_OK zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Klassen](../../atl/reference/atl-classes.md)   
 [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient-Schnittstelle](../../atl/reference/iworkerthreadclient-interface.md)
