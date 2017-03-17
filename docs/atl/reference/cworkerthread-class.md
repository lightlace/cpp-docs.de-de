---
title: CWorkerThread-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ab1c92c1b7442025f91007ef971d81d087351212
ms.lasthandoff: 02/24/2017

---
# <a name="cworkerthread-class"></a>CWorkerThread-Klasse
Diese Klasse wird ein Arbeitsthread erstellt oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernel-Objekt-Handles und eine angegebene Client-Funktion ausführt, einen Handle signalisiert wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>Parameter  
 `ThreadTraits`  
 Die Klasse, die die Thread-Erstellungsfunktion, z. B. Bereitstellung [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) oder [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-structures"></a>Geschützte Strukturen  
  
|Name|Beschreibung|  
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
|[CWorkerThread::AddHandle](#addhandle)|Rufen Sie diese Methode, um die Liste von Arbeitsthreads verwaltet ein Wait Handle des Objekts hinzugefügt.|  
|[CWorkerThread::AddTimer](#addtimer)|Rufen Sie diese Methode, um einen periodischen Wait Zeitgeber verwaltet vom Arbeitsthread hinzugefügt.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Rufen Sie diese Methode, um das Threadhandle des Arbeitsthreads erhalten.|  
|[CWorkerThread::GetThreadId](#getthreadid)|Rufen Sie diese Methode, um die Thread-ID des Arbeitsthreads erhalten.|  
|[CWorkerThread::Initialize](#initialize)|Rufen Sie diese Methode, um den Arbeitsthread zu initialisieren.|  
|[CWorkerThread::RemoveHandle](#removehandle)|Rufen Sie diese Methode, um ein Handle aus der Liste der wartbare Objekte zu entfernen.|  
|[CWorkerThread::Shutdown](#shutdown)|Rufen Sie diese Methode, um den Arbeitsthread zu schließen.|  
  
## <a name="remarks"></a>Hinweise  
  
### <a name="to-use-cworkerthread"></a>CWorkerThread verwenden  
  
1.  Erstellen Sie eine Instanz dieser Klasse.  
  
2.  Rufen Sie [CWorkerThread::Initialize](#initialize).  
  
3.  Rufen Sie [CWorkerThread::AddHandle](#addhandle) mit dem Handle des Kernel-Objekt und einen Zeiger auf eine Implementierung der [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     – oder –  
  
     Rufen Sie [CWorkerThread::AddTimer](#addtimer) mit einem Zeiger auf eine Implementierung der [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  Implementieren [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Maßnahmen zu ergreifen, wenn das Handle oder eines Zeitgebers signalisiert wird.  
  
5.  Rufen Sie zum Entfernen eines Objekts aus der Liste der Ihre [CWorkerThread::RemoveHandle](#removehandle).  
  
6.  Um den Thread zu beenden, rufen Sie [CWorkerThread::Shutdown](#shutdown).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="addhandle"></a>CWorkerThread::AddHandle  
 Rufen Sie diese Methode, um die Liste von Arbeitsthreads verwaltet ein Wait Handle des Objekts hinzugefügt.  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Das Handle für ein Wait-Objekt.  
  
 `pClient`  
 Der Zeiger auf die [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) Schnittstelle für das Objekt aufgerufen werden, wenn das Handle signalisiert wird.  
  
 `dwParam`  
 Der Parameter übergeben werden [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Wenn das Handle signalisiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) wird aufgerufen, durch `pClient` Wenn das Handle `hObject`, signalisiert wird.  
  
##  <a name="addtimer"></a>CWorkerThread::AddTimer  
 Rufen Sie diese Methode, um einen periodischen Wait Zeitgeber verwaltet vom Arbeitsthread hinzugefügt.  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwInterval*  
 Gibt den Zeitgeber in Millisekunden an.  
  
 `pClient`  
 Der Zeiger auf die [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) Schnittstelle für das Objekt aufgerufen werden, wenn das Handle signalisiert wird.  
  
 `dwParam`  
 Der Parameter übergeben werden [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Wenn das Handle signalisiert wird.  
  
 `phTimer`  
 [out] Die Adresse der HANDLE-Variablen, die bei Erfolg, das Handle für den neu erstellten Zeitgeber erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) wird aufgerufen, durch `pClient` Wenn der Zeitgeber signalisiert wird.  
  
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
 Rufen Sie diese Methode, um das Threadhandle des Arbeitsthreads erhalten.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Threadhandle oder NULL zurück, wenn der Thread nicht initialisiert wurde.  
  
##  <a name="getthreadid"></a>CWorkerThread::GetThreadId  
 Rufen Sie diese Methode, um die Thread-ID des Arbeitsthreads erhalten.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Thread-ID oder NULL zurück, wenn der Thread nicht initialisiert wurde.  
  
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
  
 Haben Sie zwei oder mehr `CWorkerThread` Objekte im gleichen Arbeitsthread verwenden, initialisieren Sie eines davon ohne Übergabe von Argumenten übergeben Sie dann einen Zeiger auf das Objekt an die `Initialize` der anderen Methoden. Die Objekte mit dem Zeiger initialisiert sollten geschlossen werden, bevor das Objekt, das zum Initialisieren verwendet.  
  
 Finden Sie unter [CWorkerThread::Shutdown](#shutdown) Informationen über das Verhalten dieser Methode wie ändert, wenn mithilfe eines Zeigers auf ein vorhandenes Objekt initialisiert.  
  
##  <a name="removehandle"></a>CWorkerThread::RemoveHandle  
 Rufen Sie diese Methode, um ein Handle aus der Liste der wartbare Objekte zu entfernen.  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hObject`  
 Das Handle zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle wird entfernt, [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) wird für das zugeordnete Objekt, das an übergebene aufgerufen [AddHandle](#addhandle). Wenn dieser Aufruf fehlschlägt, `CWorkerThread` ruft Windows [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) Funktion auf den Ziehpunkt.  
  
##  <a name="shutdown"></a>CWorkerThread::Shutdown  
 Rufen Sie diese Methode, um den Arbeitsthread zu schließen.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwWait`  
 Die Zeit in Millisekunden zu warten, bis der Arbeitsthread beendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück auf Erfolg oder Fehler HRESULT auf Fehler, z. B. wenn der Timeoutwert `dwWait`, wurde überschritten.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie das Objekt zum wiederverwenden [CWorkerThread::Initialize](#initialize) nach dem Aufrufen dieser Methode.  
  
 Beachten Sie, dass der Aufruf **Herunterfahren** auf ein Objekt mit einem Zeiger auf einen anderen initialisiert `CWorkerThread` Objekt hat keine Auswirkung und stets S_OK zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Klassen](../../atl/reference/atl-classes.md)   
 [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient-Schnittstelle](../../atl/reference/iworkerthreadclient-interface.md)

