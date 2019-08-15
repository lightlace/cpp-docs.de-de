---
title: Workerarchetype
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 7f28b9e64c88a5be440417dd9d22f129ee7d6edf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495269"
---
# <a name="worker-archetype"></a>Workerarchetype

Klassen, die dem workerarchetype entsprechen, stellen den Code bereit, mit dem Arbeitsaufgaben in einem Thread Pool verarbeitet werden.

**Implementation (Implementierung)**

Um eine Klasse zu implementieren, die diesem Archetype entspricht, muss die-Klasse die folgenden Funktionen bereitstellen:

|Methode|Beschreibung|
|------------|-----------------|
|[Initialize](#initialize)|Wird aufgerufen, um das Worker-Objekt zu initialisieren, bevor Anforderungen an [Execute](#execute)übermittelt werden.|
|[Execute](#execute)|Wird aufgerufen, um ein Arbeits Element zu verarbeiten.|
|[Terminate](#terminate)|Wird aufgerufen, um die Initialisierung des workerobjekts aufzurufen, nachdem alle Anforderungen an [Execute](#execute)übermittelt wurden.|

|TypeDef|Beschreibung|
|-------------|-----------------|
|[RequestType](#requesttype)|Eine typedef für den Typ der Arbeitsaufgabe, die von der Worker-Klasse verarbeitet werden kann.|

Eine typische *Worker* -Klasse sieht wie folgt aus:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Vorhandene Implementierungen**

Diese Klassen entsprechen diesem Archetyp:

|Klasse|Beschreibung|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen aus dem Thread Pool und übergibt sie an ein Workerobjekt, das für jede Anforderung erstellt und zerstört wird.|

**Konsum**

Diese Vorlagen Parameter erwarten, dass die Klasse diesem Archetype entspricht:

|Parameter Name|Verwendung|
|--------------------|-------------|
|*Arbeiter*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Arbeiter*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Anforderungen

**Header:** atlutil. h

## <a name="execute"></a>WorkerArchetype::Execute

Wird aufgerufen, um ein Arbeits Element zu verarbeiten.

```
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Parameter

*request*<br/>
Das zu verarbeitende Arbeits Element. Das Arbeits Element ist vom gleichen Typ wie `RequestType`.

*pvWorkerParam*<br/>
Ein benutzerdefinierter Parameter, der von der Worker-Klasse verstanden wird. Wird auch an `WorkerArchetype::Initialize` und `Terminate`übermittelt.

*pOverlapped*<br/>
Ein Zeiger auf die [über](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) Lapp Ende Struktur, die verwendet wird, um die Warteschlange zu erstellen, in der die Arbeitselemente in die Warteschlange

## <a name="initialize"></a>Workerarchetype:: Initialize

Wird aufgerufen, um das Worker-Objekt zu initialisieren, bevor `WorkerArchetype::Execute`Anforderungen an die übermittelt werden.
```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Parameter

*pvParam*<br/>
Ein benutzerdefinierter Parameter, der von der Worker-Klasse verstanden wird. Wird auch an `WorkerArchetype::Terminate` und `WorkerArchetype::Execute`übermittelt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, bei einem Fehler false.

## <a name="requesttype"></a> WorkerArchetype::RequestType

Eine typedef für den Typ der Arbeitsaufgabe, die von der Worker-Klasse verarbeitet werden kann.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Hinweise

Dieser Typ muss als erster Parameter von `WorkerArchetype::Execute` verwendet werden und muss in der Lage sein, in und aus einem ULONG_PTR umgewandelt zu werden.

## <a name="terminate"></a>Workerarchetype:: beenden

Wird aufgerufen, um die Initialisierung des workerobjekts aufzurufen, nachdem `WorkerArchetype::Execute`alle Anforderungen an übermittelt wurden.

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Parameter

*pvParam*<br/>
Ein benutzerdefinierter Parameter, der von der Worker-Klasse verstanden wird. Wird auch an `WorkerArchetype::Initialize` und `WorkerArchetype::Execute`übermittelt.

## <a name="see-also"></a>Siehe auch

[Konzepte](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)
