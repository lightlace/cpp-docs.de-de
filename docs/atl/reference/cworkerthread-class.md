---
title: CWorkerThread-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
ms.openlocfilehash: 9469770dc0538b968cfaafa2de45f28bd864193c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532001"
---
# <a name="cworkerthread-class"></a>CWorkerThread-Klasse

Diese Klasse einen Arbeitsthread erstellt oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernel-Objekt-Handles und führt eine angegebene Client-Funktion aus, wenn einem der Handles signalisiert wird.

> [!IMPORTANT]
> Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>Parameter

*ThreadTraits*<br/>
Die Klasse, die die Thread-erstellen-Funktion, wie z. B. Bereitstellung [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) oder [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).

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
|[CWorkerThread::AddHandle](#addhandle)|Rufen Sie diese Methode, um ein Objekt mit wartemöglichkeit Handle der vom Arbeitsthread verwalteten Liste hinzufügen.|
|[CWorkerThread::AddTimer](#addtimer)|Rufen Sie diese Methode, um ein periodischer mit wartemöglichkeit Timer, der vom Arbeitsthread verwalteten Liste hinzufügen.|
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Rufen Sie diese Methode rufen Sie das Threadhandle des Arbeitsthreads.|
|[CWorkerThread::GetThreadId](#getthreadid)|Rufen Sie diese Methode zum Abrufen der Thread-ID des Arbeitsthreads.|
|[CWorkerThread::Initialize](#initialize)|Rufen Sie diese Methode, um den Arbeitsthread zu initialisieren.|
|[CWorkerThread::RemoveHandle](#removehandle)|Rufen Sie diese Methode, um ein Handle aus der Liste der wartbare Objekte zu entfernen.|
|[CWorkerThread::Shutdown](#shutdown)|Rufen Sie diese Methode, um den Arbeitsthread zu schließen.|

## <a name="remarks"></a>Hinweise

### <a name="to-use-cworkerthread"></a>CWorkerThread verwenden

1. Erstellen Sie eine Instanz dieser Klasse.

1. Rufen Sie [CWorkerThread::Initialize](#initialize).

1. Rufen Sie [CWorkerThread::AddHandle](#addhandle) mit dem Handle des Kernel-Objekt und einen Zeiger auf eine Implementierung der [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).

   \- oder –

   Rufen Sie [CWorkerThread::AddTimer](#addtimer) mit einem Zeiger auf eine Implementierung der [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).

1. Implementieren [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) um Maßnahmen zu ergreifen, wenn das Handle oder Timers signalisiert wird.

1. Rufen Sie zum Entfernen eines Objekts aus der Liste der wartbare Objekte repräsentieren [CWorkerThread::RemoveHandle](#removehandle).

1. Um den Thread zu beenden, rufen Sie [CWorkerThread::Shutdown](#shutdown).

## <a name="requirements"></a>Anforderungen

**Header:** "atlutil.h"

##  <a name="addhandle"></a>  CWorkerThread::AddHandle

Rufen Sie diese Methode, um ein Objekt mit wartemöglichkeit Handle der vom Arbeitsthread verwalteten Liste hinzufügen.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>Parameter

*hObject*<br/>
Das Handle für ein Objekt mit wartemöglichkeit.

*pClient*<br/>
Der Zeiger auf die [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) Schnittstelle für das Objekt, das aufgerufen wird, wenn das Handle signalisiert wird.

*dwParam*<br/>
Der Parameter zu übergebenden [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Wenn das Handle signalisiert wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) wird aufgerufen, durch *pClient* bei der das Handle *hObject*, signalisiert wird.

##  <a name="addtimer"></a>  CWorkerThread::AddTimer

Rufen Sie diese Methode, um ein periodischer mit wartemöglichkeit Timer, der vom Arbeitsthread verwalteten Liste hinzufügen.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>Parameter

*dwInterval*<br/>
Gibt den Zeitraum des Zeitgebers in Millisekunden an.

*pClient*<br/>
Der Zeiger auf die [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) Schnittstelle für das Objekt, das aufgerufen wird, wenn das Handle signalisiert wird.

*dwParam*<br/>
Der Parameter zu übergebenden [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) Wenn das Handle signalisiert wird.

*phTimer*<br/>
[out] Adresse der HANDLE-Variable, die bei Erfolg das Handle für den neu erstellten Timer empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) wird aufgerufen, durch *pClient* Wenn der Zeitgeber signalisiert wird.

Übergeben Sie das Timer-Handle aus *PhTimer* zu [CWorkerThread::RemoveHandle](#removehandle) um den Timer zu schließen.

##  <a name="cworkerthread"></a>  CWorkerThread::CWorkerThread

Der Konstruktor.

```
CWorkerThread() throw();
```

##  <a name="dtor"></a>  CWorkerThread:: ~ CWorkerThread

Der Destruktor.

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>Hinweise

Aufrufe [CWorkerThread::Shutdown](#shutdown).

##  <a name="getthreadhandle"></a>  CWorkerThread::GetThreadHandle

Rufen Sie diese Methode rufen Sie das Threadhandle des Arbeitsthreads.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Threadhandle oder NULL zurück, wenn der Arbeitsthread nicht initialisiert wurde.

##  <a name="getthreadid"></a>  CWorkerThread::GetThreadId

Rufen Sie diese Methode zum Abrufen der Thread-ID des Arbeitsthreads.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Thread-ID oder NULL zurück, wenn der Arbeitsthread nicht initialisiert wurde.

##  <a name="initialize"></a>  CWorkerThread::Initialize

Rufen Sie diese Methode, um den Arbeitsthread zu initialisieren.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>Parameter

*pThread*<br/>
Ein Arbeitsthread.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode sollte aufgerufen werden, um das Objekt zu initialisieren, nach der Erstellung oder nach einem Aufruf von [CWorkerThread::Shutdown](#shutdown).

Haben Sie zwei oder mehr `CWorkerThread` Objekte im gleichen Arbeitsthread verwenden, initialisieren Sie einen dieser ohne Übergabe von Argumenten klicken Sie dann einen Zeiger auf das Objekt übergeben, das `Initialize` Methoden von den anderen. Die Objekte, die initialisiert wird, mit dem Zeiger sollte vor dem Objekt, das zum Initialisieren verwendeten heruntergefahren werden.

Finden Sie unter [CWorkerThread::Shutdown](#shutdown) Informationen Verhalten dieser Methode die Änderungen bei der Initialisierung mithilfe eines Zeigers auf ein vorhandenes Objekt.

##  <a name="removehandle"></a>  CWorkerThread::RemoveHandle

Rufen Sie diese Methode, um ein Handle aus der Liste der wartbare Objekte zu entfernen.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>Parameter

*hObject*<br/>
Das Handle zu entfernen.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Wenn das Handle entfernt wird [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) wird für das zugeordnete Objekt, das übergeben wurde, aufgerufen werden [AddHandle](#addhandle). Wenn dieser Aufruf fehlschlägt, `CWorkerThread` rufen die Windows ["CloseHandle"](https://msdn.microsoft.com/library/windows/desktop/ms724211) Funktion auf den Ziehpunkt.

##  <a name="shutdown"></a>  CWorkerThread::Shutdown

Rufen Sie diese Methode, um den Arbeitsthread zu schließen.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>Parameter

*dwWait*<br/>
Die Zeit in Millisekunden zu warten, bis der Arbeitsthread beendet werden soll. ATL_WORKER_THREAD_WAIT standardmäßig 10 Sekunden. Bei Bedarf können Sie einen eigenen Wert für dieses Symbol definieren, bevor "atlutil.h" einschließen.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, auf Erfolg oder einen HRESULT-Fehler bei einem Fehler, z. B. wenn der Timeoutwert *DwWait*, überschritten wird.

### <a name="remarks"></a>Hinweise

Wenn das Objekt wiederverwenden möchten, rufen Sie [CWorkerThread::Initialize](#initialize) nach dem Aufrufen dieser Methode.

Beachten Sie, dass der Aufruf `Shutdown` für ein Objekt, das mit einem Zeiger auf einen anderen initialisiert `CWorkerThread` Objekt hat keine Auswirkungen, und gibt stets S_OK zurück.

## <a name="see-also"></a>Siehe auch

[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[Klassen](../../atl/reference/atl-classes.md)<br/>
[Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md)<br/>
[IWorkerThreadClient-Schnittstelle](../../atl/reference/iworkerthreadclient-interface.md)
