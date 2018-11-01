---
title: Worker-Archetype
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: bbfe75ad996841cd4ea78adab56c7cf91ac55f3c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565554"
---
# <a name="worker-archetype"></a>Worker-Archetype

Klassen, die entsprechen, den *Worker* Archetyp Geben Sie der Code zum Arbeitsaufgaben Prozess in der Warteschlange eines Threadpools.

**Implementation (Implementierung)**

Um eine Klasse, die mit dieser Archetyp zu implementieren, muss die Klasse die folgenden Funktionen bereit:

|Methode|Beschreibung|
|------------|-----------------|
|[Initialize](#initialize)|Wird aufgerufen, um die Worker-Objekt zu initialisieren, bevor Anforderungen an übergeben werden [Execute](#execute).|
|[Execute](#execute)|Wird aufgerufen, um eine Arbeitsaufgabe zu verarbeiten.|
|[Terminate](#terminate)|Wird aufgerufen, um die Worker-Objekt Initialisierung aufheben, nachdem auf alle Anforderungen übergeben wurden [Execute](#execute).|

|TypeDef|Beschreibung|
|-------------|-----------------|
|[RequestType](#requesttype)|Eine Typedef für den Typ der Arbeitsaufgabe, die von der Klasse der workerrolle verarbeitet werden kann.|

Eine typische *Worker* Klasse sieht wie folgt aus:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Vorhandene Implementierungen**

Dieser Archetyp entsprechen diesen Klassen:

|Klasse|Beschreibung|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen von Threadpool der Warteschleife hinzu und übergibt sie an eine Worker-Objekt, das erstellt und zerstört für jede Anforderung.|

**Verwendung**

Diese Vorlagenparameter erwarten, dass die Klasse, um dieser Archetyp entsprechen:

|Name des Parameters|Verwendung|
|--------------------|-------------|
|*Worker*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Worker*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Anforderungen

**Header:** "atlutil.h"

## <a name="execute"></a>WorkerArchetype::Execute

Wird aufgerufen, um eine Arbeitsaufgabe zu verarbeiten.

```
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Parameter

*Anforderung*<br/>
Die Arbeitsaufgabe verarbeitet werden. Das Arbeitselement ist vom gleichen Typ wie `RequestType`.

*pvWorkerParam*<br/>
Einen benutzerdefinierten Parameter, der verstanden werden, durch die Workerklasse. Auch an übergeben `WorkerArchetype::Initialize` und `Terminate`.

*"pOverlapped"*<br/>
Ein Zeiger auf die [OVERLAPPED](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped) Struktur verwendet, um die Warteschlange zu erstellen, auf welche Elemente wurden in die Warteschlange eingereiht.

## <a name="initialize"></a> WorkerArchetype::Initialize

Wird aufgerufen, um die Worker-Objekt zu initialisieren, bevor Anforderungen an übergeben werden `WorkerArchetype::Execute`.
```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Parameter

*pvParam*<br/>
Einen benutzerdefinierten Parameter, der verstanden werden, durch die Workerklasse. Auch an übergeben `WorkerArchetype::Terminate` und `WorkerArchetype::Execute`.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, bei Erfolg bei "false".

## <a name="requesttype"></a> WorkerArchetype::RequestType

Eine Typedef für den Typ der Arbeitsaufgabe, die von der Klasse der workerrolle verarbeitet werden kann.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Hinweise

Dieser Typ muss verwendet werden, als der erste Parameter der `WorkerArchetype::Execute` muss in und aus einem ULONG_PTR umgewandelt werden kann.

## <a name="terminate"></a> WorkerArchetype::Terminate

Wird aufgerufen, um die Worker-Objekt Initialisierung aufheben, nachdem auf alle Anforderungen übergeben wurden `WorkerArchetype::Execute`).

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Parameter

*pvParam*<br/>
Einen benutzerdefinierten Parameter, der verstanden werden, durch die Workerklasse. Auch an übergeben `WorkerArchetype::Initialize` und `WorkerArchetype::Execute`.

## <a name="see-also"></a>Siehe auch

[Konzepte](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)

