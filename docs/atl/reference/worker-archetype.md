---
title: Worker Urtyp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ff0e71e15c70d8d5d9dee0b398d4f0c075eb47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="worker-archetype"></a>Worker Urtyp
Klassen, die entsprechen, den *Worker* Urtyp Geben Sie der Code zum Verarbeiten von Arbeitselementen in der Warteschlange eines Threadpools.  
  
 **Implementation (Implementierung)**  
  
 Um eine Klasse, die mit diesem Urtyp implementieren zu können, muss die Klasse die folgenden Funktionen bereit:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Initialize](#initialize)|Wird aufgerufen, um die Worker-Objekt zu initialisieren, bevor alle Anforderungen an weitergegeben werden [Execute](#execute).|  
|[Führen Sie](#execute)|Wird aufgerufen, um eine Arbeitsaufgabe zu verarbeiten.|  
|[Beenden](#terminate)|Wird aufgerufen, um die Worker-Objekt Initialisierung aufheben, nachdem alle Anforderungen an übergeben wurden [Execute](#execute).|  
  
|TypeDef|Beschreibung|  
|-------------|-----------------|  
|[RequestType](#requesttype)|Eine Typedef für den Typ der Arbeitsaufgabe, die von der Workerklasse verarbeitet werden kann.|  
  
 Eine typische *Worker* Klasse sieht wie folgt aus:  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **Vorhandenen Implementierungen**  
  
 Diese Klassen entsprechen diese Urtyp:  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen aus dem Threadpool und übergibt diese an einen Worker-Objekt, das erstellt und zerstört für jede Anforderung.|  
  
 **Verwendung**  
  
 Diese Vorlagenparameter erwarten, dass die Klasse diese Urtyp entsprechen:  
  
|Parametername|Verwendung|  
|--------------------|-------------|  
|*Worker*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*Worker*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
Wird aufgerufen, um eine Arbeitsaufgabe zu verarbeiten.  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>Parameter  
 `request`  
 Die Arbeitsaufgabe verarbeitet werden. Die Arbeitsaufgabe wird vom gleichen Typ wie `RequestType`.  
  
 `pvWorkerParam`  
 Einen benutzerdefinierten Parameter verständlich die Workerklasse. Auch an übergeben `WorkerArchetype::Initialize` und `Terminate`.  
  
 `pOverlapped`  
 Ein Zeiger auf die [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) Struktur verwendet, um die Warteschlange zu erstellen, auf welche Elemente wurden in die Warteschlange eingereiht.  
  
## <a name="initialize"></a> WorkerArchetype::Initialize
Wird aufgerufen, um die Worker-Objekt zu initialisieren, bevor alle Anforderungen an weitergegeben werden `WorkerArchetype::Execute`.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parameter  
 `pvParam`  
 Einen benutzerdefinierten Parameter verständlich die Workerklasse. Auch an übergeben `WorkerArchetype::Terminate` und `WorkerArchetype::Execute`.  
  
### <a name="return-value"></a>Rückgabewert  
 Zurückgeben **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
## <a name="requesttype"></a> WorkerArchetype::RequestType
Eine Typedef für den Typ der Arbeitsaufgabe, die von der Workerklasse verarbeitet werden kann.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Typ muss verwendet werden, als der erste Parameter der `WorkerArchetype::Execute` und der umzuwandelnden verschiedene andere und aus einem ULONG_PTR in der Lage sein muss.  
  
## <a name="terminate"></a> WorkerArchetype::Terminate
Wird aufgerufen, um die Worker-Objekt Initialisierung aufheben, nachdem alle Anforderungen an übergeben wurden `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parameter  
 `pvParam`  
 Einen benutzerdefinierten Parameter verständlich die Workerklasse. Auch an übergeben `WorkerArchetype::Initialize` und `WorkerArchetype::Execute`.  
  
## <a name="see-also"></a>Siehe auch  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)



