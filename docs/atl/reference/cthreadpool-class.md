---
title: CThreadPool-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: f55f7d676988e43216adbf6e8a0b6c21afd958a3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884086"
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
 Die Klasse, die mit der [Worker Archetyp](../../atl/reference/worker-archetype.md) den Code zum Verarbeiten von Arbeitsvorgängen Elemente in der Warteschlange im Threadpool verwendet bereitstellen.  
  
 *ThreadTraits*  
 Die Klasse der Funktion verwendet, um die Threads im Pool zu erstellen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|Der Konstruktor für den Threadpool.|  
|[CThreadPool:: ~ CThreadPool](#dtor)|Der Destruktor für Threadpool der Warteschleife hinzu.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|Implementierung von `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](#getnumthreads)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool verfügbar machen.|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|Rufen Sie diese Methode, um das Handle des e/a-Abschlussport zum Arbeitsaufgaben in die Warteschlange abrufen.|  
|[:: GetSize](#getsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool verfügbar machen.|  
|[CThreadPool::GetTimeout](#gettimeout)|Rufen Sie diese Methode rufen Sie die maximale Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.|  
|[CThreadPool::Initialize](#initialize)|Rufen Sie diese Methode zum Initialisieren der Threadpool der Warteschleife hinzu.|  
|[CThreadPool::QueryInterface](#queryinterface)|Implementierung von `IUnknown::QueryInterface`.|  
|[CThreadPool::QueueRequest](#queuerequest)|Rufen Sie diese Methode, um in die Warteschlange ein Arbeitselement von einem Thread im Pool verarbeitet werden.|  
|[CThreadPool::Release](#release)|Implementierung von `IUnknown::Release`.|  
|[Wurde](#setsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool festlegen.|  
|[CThreadPool::SetTimeout](#settimeout)|Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.|  
|[CThreadPool::Shutdown](#shutdown)|Rufen Sie diese Methode zum Herunterfahren der Threadpool der Warteschleife hinzu.|  
  
## <a name="remarks"></a>Hinweise  
 Threads im Pool erstellt und zerstört, wenn der Pool ist initialisiert, Größe oder Herunterfahren. Eine Instanz der Klasse *Worker* auf dem Stapel jeder Arbeitsthread im Pool erstellt werden. Jede Instanz wird für die Lebensdauer des Threads befinden.  
  
 Unmittelbar nach der Erstellung eines Threads *Worker*:: `Initialize` lautet für das Objekt, das diesem Thread zugeordnet. Unmittelbar vor der Zerstörung eines Threads *Worker*:: `Terminate` aufgerufen wird. Beide Methoden akzeptieren eine **"void"\***  Argument. Der Wert dieses Arguments wird an den Threadpool durch Übergeben der *PvWorkerParam* Parameter [CThreadPool::Initialize](#initialize).  
  
 Wenn Arbeitsaufgaben in die Warteschlange und den Worker-Threads verfügbar sind für die Arbeit, wird ein Arbeitsthread abrufen ein Elements aus der Warteschlange und rufen die `Execute` Methode der *Worker* Objekt für diesen Thread. Drei Elemente werden dann an die Methode übergeben: das Element aus der Warteschlange, die gleiche `pvWorkerParam` übergeben *Worker*:: `Initialize` und *Worker*:: `Terminate`, und einen Zeiger auf die [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) Struktur, die für die e/a-Abschluss-Port-Warteschlange verwendet.  
  
 Die *Worker* Klasse deklariert den Typ der Elemente, die für den Threadpool in Warteschlangen gestellt werden durch die Bereitstellung einer Typedef, *Worker*:: `RequestType`. Dieser Typ muss in und aus einem ULONG_PTR umgewandelt werden können.  
  
 Ein Beispiel für eine *Worker* Klasse [CNonStatelessWorker-Klasse](../../atl/reference/cnonstatelessworker-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlutil.h"  
  
##  <a name="addref"></a>  CThreadPool::AddRef  
 Implementierung von `IUnknown::AddRef`.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert nicht die lebensdauersteuerung mit verweiszählung.  
  
##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool  
 Der Konstruktor für den Threadpool.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Den Timeoutwert, der ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT wird initialisiert. Die Standardzeit beträgt 36 Sekunden. Bei Bedarf können Sie eigene positive ganze Zahl für dieses Symbol definieren, bevor "atlutil.h" einschließen.  
  
##  <a name="dtor"></a>  CThreadPool:: ~ CThreadPool  
 Der Destruktor für Threadpool der Warteschleife hinzu.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [CThreadPool::Shutdown](#shutdown).  
  
##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool verfügbar machen.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Threads im Pool zurück.  
  
##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle  
 Rufen Sie diese Methode, um das Handle des e/a-Abschlussport zum Arbeitsaufgaben in die Warteschlange abrufen.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt zurück, der Warteschlangenhandle oder NULL, wenn es sich bei der Threadpool nicht initialisiert wurde.  
  
##  <a name="getsize"></a>  :: GetSize  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool verfügbar machen.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pnNumThreads*  
 [out] Die Adresse der Variablen, die bei Erfolg die Anzahl der Threads im Pool empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="gettimeout"></a>  CThreadPool::GetTimeout  
 Rufen Sie diese Methode rufen Sie die maximale Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pdwMaxWait*  
 [out] Die Adresse der Variablen, die bei Erfolg die maximale Zeit in Millisekunden empfängt, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Timeoutwert wird verwendet, indem [CThreadPool::Shutdown](#shutdown) Wenn kein anderer Wert für diese Methode angegeben wird.  
  
##  <a name="initialize"></a>  CThreadPool::Initialize  
 Rufen Sie diese Methode zum Initialisieren der Threadpool der Warteschleife hinzu.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pvWorkerParam*  
 Der Worker-Parameter auf des Threadobjekts Worker zu übergebenden `Initialize`, `Execute`, und `Terminate` Methoden.  
  
 *nNumThreads*  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn *nNumThreads* ist negativ, der Absolute Wert multipliziert die Anzahl der Prozessoren auf dem Computer, der die Gesamtzahl der Threads abzurufen.  
  
 Wenn *nNumThreads* ist 0 (null), ATLS_DEFAULT_THREADSPERPROC multipliziert die Anzahl der Prozessoren auf dem Computer, der die Gesamtzahl der Threads abzurufen.  Der Standardwert ist 2 Threads pro Prozessor fest. Bei Bedarf können Sie eigene positive ganze Zahl für dieses Symbol definieren, bevor "atlutil.h" einschließen.
  
 *dwStackSize*  
 Die Stapelgröße für jeden Thread im Pool.  
  
 *hCompletion*  
 Das Handle eines Objekts der Abschlussport zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="queryinterface"></a>  CThreadPool::QueryInterface  
 Implementierung von `IUnknown::QueryInterface`.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Objekte dieser Klasse können erfolgreich abgefragt werden, für die `IUnknown` und [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) Schnittstellen.  
  
##  <a name="queuerequest"></a>  CThreadPool::QueueRequest  
 Rufen Sie diese Methode, um in die Warteschlange ein Arbeitselement von einem Thread im Pool verarbeitet werden.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *Anforderung*  
 Die Anforderung in die Warteschlange gestellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg bei "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt ein Arbeitselement in die Warteschlange. Die Threads im Pool wählen Sie Elemente aus der Warteschlange in der Reihenfolge, in der sie empfangen werden.  
  
##  <a name="release"></a>  CThreadPool::Release  
 Implementierung von `IUnknown::Release`.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert nicht die lebensdauersteuerung mit verweiszählung.  
  
##  <a name="setsize"></a>  Wurde  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool festlegen.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nNumThreads*  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn *nNumThreads* ist negativ, der Absolute Wert multipliziert die Anzahl der Prozessoren auf dem Computer, der die Gesamtzahl der Threads abzurufen.  
  
 Wenn *nNumThreads* ist 0 (null), ATLS_DEFAULT_THREADSPERPROC multipliziert die Anzahl der Prozessoren auf dem Computer, der die Gesamtzahl der Threads abzurufen. Der Standardwert ist 2 Threads pro Prozessor fest. Bei Bedarf können Sie eigene positive ganze Zahl für dieses Symbol definieren, bevor "atlutil.h" einschließen.
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anzahl der angegebenen Threads kleiner als die Anzahl der Threads im Pool derzeit ist, erhält das Objekt eine Nachricht zum Herunterfahren in der Warteschlange von wartenden Threads übernommen werden. Wenn ein wartender Thread die Nachricht aus der Warteschlange abruft, benachrichtigt der Threadpool der Warteschleife hinzu und beendet die Threadprozedur. Dieser Prozess wird wiederholt, bis die Anzahl der Threads im Pool für die angegebene Anzahl erreicht oder kein Thread innerhalb des Zeitraums, indem Sie beendet wurde [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). In diesem Fall gibt die Methode WAIT_TIMEOUT entsprechenden HRESULT zurück, und die ausstehenden Herunterfahren-Nachricht abgebrochen wird.  
  
##  <a name="settimeout"></a>  CThreadPool::SetTimeout  
 Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwMaxWait*  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Timeout wird mit ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT initialisiert. Die Standardzeit beträgt 36 Sekunden. Bei Bedarf können Sie eigene positive ganze Zahl für dieses Symbol definieren, bevor "atlutil.h" einschließen. 
  
 Beachten Sie, dass *DwMaxWait* die Zeit, die der Pool, für einen einzelnen Thread gewartet wird beendet wird. Die maximale Zeit, die ausgeführt werden kann, um mehrere Threads aus dem Pool entfernen möglicherweise etwas weniger als *DwMaxWait* multipliziert die Anzahl der Threads.  
  
##  <a name="shutdown"></a>  CThreadPool::Shutdown  
 Rufen Sie diese Methode zum Herunterfahren der Threadpool der Warteschleife hinzu.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwMaxWait*  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool für einen Thread zum Herunterfahren gewartet wird. Wenn 0 oder kein Wert angegeben wird, diese Methode verwendet den Timeout festlegen, indem [CThreadPool::SetTimeout](#settimeout).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet eine Anforderung zum Herunterfahren für alle Threads im Pool. Wenn das Timeout abläuft, ruft diese Methode [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717) in jedem Thread aus, das nicht beendet. Diese Methode wird vom Destruktor der Klasse automatisch aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [IThreadPoolConfig-Schnittstelle](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Klassen](../../atl/reference/atl-classes.md)
