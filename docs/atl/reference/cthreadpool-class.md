---
title: CThreadPool-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CThreadPool
- ATL::CThreadPool
- CThreadPool
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: 22
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
ms.openlocfilehash: 632514d03e7037ef42a1566462db5dec6f5cc1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cthreadpool-class"></a>CThreadPool-Klasse
Diese Klasse stellt einen Pool von Arbeitsthreads, die eine Warteschlange von Arbeitsaufgaben zu verarbeiten.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>Parameter  
 *Worker*  
 Die Klasse, die mit der [Worker Prototyp](../../atl/reference/worker-archetype.md) Bereitstellen des Codes zum Verarbeiten von Arbeitsvorgängen Elemente in der Warteschlange für den Threadpool verwendet.  
  
 `ThreadTraits`  
 Die Klasse der Funktion verwendet, um die Threads im Pool zu erstellen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|Der Konstruktor für den Threadpool.|  
|[CThreadPool:: ~ CThreadPool](#dtor)|Der Destruktor für den Threadpool.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|Implementierung von `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](#getnumthreads)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|Rufen Sie diese Methode, um das Handle des e/a-Abschlussport verwendet, um Arbeitsaufgaben in die Warteschlange abrufen.|  
|[:: GetSize](#getsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.|  
|[CThreadPool::GetTimeout](#gettimeout)|Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool, bis ein Thread warten soll beendet.|  
|[CThreadPool::Initialize](#initialize)|Rufen Sie diese Methode, um den Threadpool zu initialisieren.|  
|[CThreadPool::QueryInterface](#queryinterface)|Implementierung von **IUnknown:: QueryInterface**.|  
|[CThreadPool::QueueRequest](#queuerequest)|Rufen Sie diese Methode, um eine Arbeitsaufgabe von einem Thread im Pool verarbeitet werden.|  
|[CThreadPool::Release](#release)|Implementierung von `IUnknown::Release`.|  
|[Wurde](#setsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.|  
|[CThreadPool::SetTimeout](#settimeout)|Rufen Sie diese Methode, um die maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet.|  
|[CThreadPool::Shutdown](#shutdown)|Rufen Sie diese Methode, um den Threadpool zu schließen.|  
  
## <a name="remarks"></a>Hinweise  
 Threads im Pool erstellt und zerstört, wenn der Pool initialisiert, geändert oder Herunterfahren. Eine Instanz der Klasse *Worker* auf dem Stapel von jeder Arbeitsthread im Pool erstellt werden. Jede Instanz werden für die Lebensdauer des Threads gespeichert.  
  
 Unmittelbar nach der Erstellung eines Threads *Worker*:: `Initialize` wird auf dem Objekt zugeordneten Threads aufgerufen werden. Unmittelbar vor der Zerstörung eines Threads *Worker*:: `Terminate` aufgerufen wird. Beide Methoden akzeptieren müssen ein **void\* ** Argument. Der Wert dieses Arguments wird an den Threadpool durch Übergeben der `pvWorkerParam` Parameter der [CThreadPool::Initialize](#initialize).  
  
 Wenn Arbeitsaufgaben in die Warteschlange und Worker-Threads verfügbar sind für die Arbeit, ein Arbeitsthread wird ziehen Sie ein Element aus der Warteschlange und rufen die **ausführen** Methode der *Worker* Objekt für diesen Thread. Drei Elemente werden dann an die Methode übergeben: das Element aus der Warteschlange, die gleiche `pvWorkerParam` übergeben *Worker*:: `Initialize` und *Worker*:: `Terminate`, und ein Zeiger auf die [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) Struktur für die e/a-Abschluss Port-Warteschlange verwendet.  
  
 Die *Worker* Klasse deklariert den Typ der Elemente, die für den Threadpool in die Warteschlange eingereiht wird durch die Bereitstellung einer Typedef *Worker*:: `RequestType`. Dieser Typ muss der umgewandelt wird, und kann einen **ULONG_PTR**.  
  
 Ein Beispiel für eine *Worker* -Klasse ist [CNonStatelessWorker Klasse](../../atl/reference/cnonstatelessworker-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="a-nameaddrefa--cthreadpooladdref"></a><a name="addref"></a>CThreadPool::AddRef  
 Implementierung von `IUnknown::AddRef`.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert die Lebensdauer-Steuerelement mit dem zählen der Verweise nicht.  
  
##  <a name="a-namecthreadpoola--cthreadpoolcthreadpool"></a><a name="cthreadpool"></a>CThreadPool::CThreadPool  
 Der Konstruktor für den Threadpool.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert den Timeoutwert für [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10).  
  
##  <a name="a-namedtora--cthreadpoolcthreadpool"></a><a name="dtor"></a>CThreadPool:: ~ CThreadPool  
 Der Destruktor für den Threadpool.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CThreadPool::Shutdown](#shutdown).  
  
##  <a name="a-namegetnumthreadsa--cthreadpoolgetnumthreads"></a><a name="getnumthreads"></a>CThreadPool::GetNumThreads  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Threads im Pool.  
  
##  <a name="a-namegetqueuehandlea--cthreadpoolgetqueuehandle"></a><a name="getqueuehandle"></a>CThreadPool::GetQueueHandle  
 Rufen Sie diese Methode, um das Handle des e/a-Abschlussport verwendet, um Arbeitsaufgaben in die Warteschlange abrufen.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt zurück, der Warteschlangenhandle oder NULL, wenn der Threadpool nicht initialisiert wurde.  
  
##  <a name="a-namegetsizea--cthreadpoolgetsize"></a><a name="getsize"></a>:: GetSize  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pnNumThreads`  
 [out] Die Adresse der Variablen, die bei Erfolg, die Anzahl der Threads im Pool empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namegettimeouta--cthreadpoolgettimeout"></a><a name="gettimeout"></a>CThreadPool::GetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool, bis ein Thread warten soll beendet.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pdwMaxWait`  
 [out] Die Adresse der Variablen, die bei Erfolg die maximale Zeit in Millisekunden, die der Threadpool warten soll, bis ein Thread erhält beendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Timeoutwert werden [CThreadPool::Shutdown](#shutdown) Wenn kein anderer Wert für diese Methode angegeben wird.  
  
##  <a name="a-nameinitializea--cthreadpoolinitialize"></a><a name="initialize"></a>CThreadPool::Initialize  
 Rufen Sie diese Methode, um den Threadpool zu initialisieren.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pvWorkerParam`  
 Der Worker-Parameter an die Worker-Thread-Objekt übergeben werden `Initialize`, **ausführen**, und `Terminate` Methoden.  
  
 `nNumThreads`  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn `nNumThreads` ist negativ, der Absolute Wert multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
 Wenn `nNumThreads` NULL ist, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
 `dwStackSize`  
 Die Stapelgröße für jeden Thread im Pool.  
  
 *hCompletion*  
 Das Handle eines Objekts Abschlussport zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namequeryinterfacea--cthreadpoolqueryinterface"></a><a name="queryinterface"></a>CThreadPool::QueryInterface  
 Implementierung von **IUnknown:: QueryInterface**.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Objekte dieser Klasse können erfolgreich abgefragt werden, für die **IUnknown** und [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) Schnittstellen.  
  
##  <a name="a-namequeuerequesta--cthreadpoolqueuerequest"></a><a name="queuerequest"></a>CThreadPool::QueueRequest  
 Rufen Sie diese Methode, um eine Arbeitsaufgabe von einem Thread im Pool verarbeitet werden.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `request`  
 Die Anforderung in die Warteschlange gestellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt eine Arbeitsaufgabe in die Warteschlange. Die Threads im Pool wählen Sie Elemente aus der Warteschlange in der Reihenfolge, in der sie empfangen werden.  
  
##  <a name="a-namereleasea--cthreadpoolrelease"></a><a name="release"></a>CThreadPool::Release  
 Implementierung von `IUnknown::Release`.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert die Lebensdauer-Steuerelement mit dem zählen der Verweise nicht.  
  
##  <a name="a-namesetsizea--cthreadpoolsetsize"></a><a name="setsize"></a>Wurde  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nNumThreads`  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn `nNumThreads` ist negativ, der Absolute Wert multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
 Wenn `nNumThreads` NULL ist, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anzahl der angegebenen Threads kleiner als die Anzahl der Threads im Pool aktuell ist, stellt das Objekt eine Nachricht für das Herunterfahren in die Warteschlange, die durch einen wartenden Thread abgerufen wird. Wenn ein wartenden Thread die Nachricht aus der Warteschlange entnimmt, benachrichtigt den Threadpool und die Threadprozedur beendet. Dieser Prozess wird wiederholt, bis die Anzahl der Threads im Pool für die angegebene Anzahl erreicht oder innerhalb des angegebenen Zeitraums kein Thread beendet wurde [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). In diesem Fall die Methode gibt ein HRESULT entspricht **WAIT_TIMEOUT** und die ausstehende Herunterfahren-Nachricht wird abgebrochen.  
  
##  <a name="a-namesettimeouta--cthreadpoolsettimeout"></a><a name="settimeout"></a>CThreadPool::SetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwMaxWait`  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Timeout wird initialisiert, um [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10) im Konstruktor.  
  
 Beachten Sie, dass `dwMaxWait` ist die Zeit, die der Pool für einen Thread für die Beendigung wartet. Die maximale Zeit, die ergriffen werden könnten, um mehrere Threads aus dem Pool entfernen möglicherweise etwas weniger als `dwMaxWait` multipliziert mit der Anzahl der Threads.  
  
##  <a name="a-nameshutdowna--cthreadpoolshutdown"></a><a name="shutdown"></a>CThreadPool::Shutdown  
 Rufen Sie diese Methode, um den Threadpool zu schließen.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwMaxWait`  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet wird. Wenn 0 oder kein Wert angegeben wird, verwendet diese Methode das Timeout festlegen, indem Sie [CThreadPool::SetTimeout](#settimeout).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet eine Anforderung zum Herunterfahren für alle Threads im Pool. Diese Methode wird aufgerufen, wenn das Timeout abläuft, [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717) für jeden Thread, der nicht beendet. Diese Methode wird vom Destruktor der Klasse automatisch aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [IThreadPoolConfig-Schnittstelle](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Klassen](../../atl/reference/atl-classes.md)

