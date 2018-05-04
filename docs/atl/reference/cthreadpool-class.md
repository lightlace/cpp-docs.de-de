---
title: CThreadPool Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64a165bdffa9f37241991af919d60de2e0dc7a96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
 Die Klasse, die mit der [Worker Urtyp](../../atl/reference/worker-archetype.md) den Code zum Verarbeiten von Arbeitsvorgängen Elemente in der Warteschlange auf den Threadpool verwendet bereitstellen.  
  
 `ThreadTraits`  
 Die Klasse der Funktion verwendet, um die Threads im Pool zu erstellen.  
  
## <a name="members"></a>Member  
  
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
|[CThreadPool::GetQueueHandle](#getqueuehandle)|Rufen Sie diese Methode, um das Handle von der e/a-Abschlussport verwendet, um Arbeitsaufgaben in die Warteschlange zu erhalten.|  
|[:: GetSize](#getsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.|  
|[CThreadPool::GetTimeout](#gettimeout)|Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool darauf gewartet, dass ein Thread beendet wird.|  
|[CThreadPool::Initialize](#initialize)|Rufen Sie diese Methode, um die Threadpools zu initialisieren.|  
|[CThreadPool::QueryInterface](#queryinterface)|Implementierung von **IUnknown:: QueryInterface**.|  
|[CThreadPool::QueueRequest](#queuerequest)|Rufen Sie diese Methode, um eine Arbeitsaufgabe von einem Thread im Pool behandelt werden in die Warteschlange ein.|  
|[CThreadPool::Release](#release)|Implementierung von `IUnknown::Release`.|  
|[Wurde](#setsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.|  
|[CThreadPool::SetTimeout](#settimeout)|Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool darauf gewartet, dass ein Thread beendet wird.|  
|[CThreadPool::Shutdown](#shutdown)|Rufen Sie diese Methode, um den Threadpool zu schließen.|  
  
## <a name="remarks"></a>Hinweise  
 Threads im Pool erstellt und zerstört, wenn der Pool initialisiert, Größe oder Herunterfahren. Eine Instanz der Klasse *Worker* auf dem Stapel der einzelnen Worker-Threads im Pool erstellt werden. Jede Instanz bestehen für die Lebensdauer des Threads.  
  
 Direkt nach dem Erstellen eines Threads *Worker*:: `Initialize` wird aufgerufen, für das Objekt, das diesem Thread zugeordnet. Unmittelbar vor der Zerstörung eines Threads *Worker*:: `Terminate` aufgerufen wird. Beide Methoden akzeptieren müssen eine **"void"\***  Argument. Der Wert dieses Arguments wird an den Threadpool durch Übergeben der `pvWorkerParam` Parameter [CThreadPool::Initialize](#initialize).  
  
 Wenn Arbeitsaufgaben in die Warteschlange und Worker-Threads verfügbar sind für die Arbeit, ein Arbeitsthread Ruft ein Element aus der Warteschlange und rufen die **Execute** Methode der *Worker* Objekt für diesen Thread. Drei Elemente werden dann an die Methode übergeben: das Element aus der Warteschlange, die gleiche `pvWorkerParam` übergeben *Worker*:: `Initialize` und *Worker*:: `Terminate`, und ein Zeiger auf die [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) Struktur, die für die e/a-Port beendigungswarteschlange verwendet.  
  
 Die *Worker* Klasse deklariert den Typ der Elemente, die im Threadpool in die Warteschlange eingereiht wird durch die Bereitstellung einer Typedef *Worker*:: `RequestType`. Dieser Typ muss kann umzuwandelnden in und aus einem **ULONG_PTR**.  
  
 Ein Beispiel für eine *Worker* Klasse ist [CNonStatelessWorker Klasse](../../atl/reference/cnonstatelessworker-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="addref"></a>  CThreadPool::AddRef  
 Implementierung von `IUnknown::AddRef`.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert nicht die Lebensdauer-Steuerelement mit dem verweiszählung.  
  
##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool  
 Der Konstruktor für den Threadpool.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert den Timeoutwert zu `ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT`. Die Standardzeit beträgt 36 Sekunden. Bei Bedarf können Sie eigene positiven ganzzahligen Wert für dieses Symbol vor dem Einfügen von atlutil.h definieren.  
  
##  <a name="dtor"></a>  CThreadPool:: ~ CThreadPool  
 Der Destruktor für den Threadpool.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CThreadPool::Shutdown](#shutdown).  
  
##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Threads im Pool zurück.  
  
##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle  
 Rufen Sie diese Methode, um das Handle von der e/a-Abschlussport verwendet, um Arbeitsaufgaben in die Warteschlange zu erhalten.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Threadpool wurde nicht initialisiert die Warteschlangenhandle oder NULL zurückgegeben werden soll.  
  
##  <a name="getsize"></a>  :: GetSize  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pnNumThreads`  
 [out] Die Adresse der Variablen, die bei Erfolg, die Anzahl der Threads im Pool empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="gettimeout"></a>  CThreadPool::GetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pdwMaxWait`  
 [out] Die Adresse der Variablen, die bei Erfolg, die maximale Zeit in Millisekunden empfängt, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Timeoutwert wird verwendet, indem [CThreadPool::Shutdown](#shutdown) Wenn kein anderer Wert für diese Methode angegeben wird.  
  
##  <a name="initialize"></a>  CThreadPool::Initialize  
 Rufen Sie diese Methode, um die Threadpools zu initialisieren.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pvWorkerParam`  
 Der Worker-Parameter an des Threadobjekts Worker zu übergebenden `Initialize`, **Execute**, und `Terminate` Methoden.  
  
 `nNumThreads`  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn `nNumThreads` ist negativ ist, dessen absoluter Wert multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtanzahl der Threads abzurufen.  
  
 Wenn `nNumThreads` ist 0 (null), `ATLS_DEFAULT_THREADSPERPROC` multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtanzahl der Threads abzurufen.  Der Standardwert ist 2 Threads pro Prozessor an. Bei Bedarf können Sie eigene positiven ganzzahligen Wert für dieses Symbol vor dem Einfügen von atlutil.h definieren.
  
 `dwStackSize`  
 Die Stapelgröße für jeden Thread im Pool.  
  
 *hCompletion*  
 Das Handle eines Objekts der Abschlussport zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="queryinterface"></a>  CThreadPool::QueryInterface  
 Implementierung von **IUnknown:: QueryInterface**.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Objekte dieser Klasse können erfolgreich abgefragt werden, für die **IUnknown** und [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) Schnittstellen.  
  
##  <a name="queuerequest"></a>  CThreadPool::QueueRequest  
 Rufen Sie diese Methode, um eine Arbeitsaufgabe von einem Thread im Pool behandelt werden in die Warteschlange ein.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `request`  
 Die Anforderung in die Warteschlange gestellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt eine Arbeitsaufgabe in die Warteschlange. Die Threads im Pool wählen Sie Elemente aus der Warteschlange in der Reihenfolge, in der sie empfangen werden.  
  
##  <a name="release"></a>  CThreadPool::Release  
 Implementierung von `IUnknown::Release`.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert nicht die Lebensdauer-Steuerelement mit dem verweiszählung.  
  
##  <a name="setsize"></a>  Wurde  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nNumThreads`  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn `nNumThreads` ist negativ ist, dessen absoluter Wert multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtanzahl der Threads abzurufen.  
  
 Wenn `nNumThreads` ist 0 (null), `ATLS_DEFAULT_THREADSPERPROC` multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtanzahl der Threads abzurufen. Der Standardwert ist 2 Threads pro Prozessor an. Bei Bedarf können Sie eigene positiven ganzzahligen Wert für dieses Symbol vor dem Einfügen von atlutil.h definieren.
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anzahl der angegebenen Threads kleiner als die Anzahl der Threads im Pool aktuell ist, stellt das Objekt eine Nachricht über das Herunterfahren in die Warteschlange, indem Sie einen wartenden Thread abgerufen zu werden. Wenn Sie ein wartenden Thread die Nachricht aus der Warteschlange abruft, benachrichtigt den Threadpool und die Threadprozedur beendet. Dieser Prozess wird wiederholt, bis die Anzahl der Threads im Pool für die angegebene Anzahl erreicht oder keine Threads innerhalb des Zeitraums gemäß beinhalten [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). In diesem Fall gibt die Methode zurück, ein HRESULT entspricht **WAIT_TIMEOUT** und die Nachricht über das ausstehende Herunterfahren abgebrochen wird.  
  
##  <a name="settimeout"></a>  CThreadPool::SetTimeout  
 Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwMaxWait`  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Timeout wird initialisiert, um `ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT`. Die Standardzeit beträgt 36 Sekunden. Bei Bedarf können Sie eigene positiven ganzzahligen Wert für dieses Symbol vor dem Einfügen von atlutil.h definieren. 
  
 Beachten Sie, dass `dwMaxWait` ist die Zeit, die einen einzelnen Thread zum Herunterfahren der Pool gewartet wird. Die maximale Zeit, die ausgeführt werden konnte, um mehrere Threads aus dem Pool entfernt möglicherweise etwas weniger als `dwMaxWait` multipliziert die Anzahl der Threads.  
  
##  <a name="shutdown"></a>  CThreadPool::Shutdown  
 Rufen Sie diese Methode, um den Threadpool zu schließen.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwMaxWait`  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool darauf gewartet, dass ein Thread beendet wird. Wenn 0 oder kein Wert angegeben wird, verwendet diese Methode den Timeout festlegen, indem [CThreadPool::SetTimeout](#settimeout).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet eine Anforderung zum Herunterfahren für alle Threads im Pool. Diese Methode wird aufgerufen, wenn das Timeout abläuft, [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717) für jeden Thread, der nicht beendet. Diese Methode wird von der Destruktor der Klasse automatisch aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [IThreadPoolConfig-Schnittstelle](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Klassen](../../atl/reference/atl-classes.md)
