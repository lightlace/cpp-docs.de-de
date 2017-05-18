---
title: Worker Prototyp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 046160644cca3bd23e4293a3c52692d2b4c94cd5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="worker-archetype"></a>Worker-Prototyp
Klassen, die entsprechen, den *Worker* Prototyp Geben Sie der Code zum Verarbeiten von Arbeitsaufgaben in der Warteschlange eines Threadpools.  
  
 **Implementierung**  
  
 Um eine Klasse, die mit diesem Prototyp zu implementieren, muss die Klasse die folgenden Funktionen bereitstellen:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Initialisieren](#initialize)|Wird aufgerufen, um das Worker-Objekt zu initialisieren, bevor Anforderungen an übergeben werden [Execute](#execute).|  
|[Ausführen](#execute)|Wird aufgerufen, um eine Arbeitsaufgabe zu verarbeiten.|  
|[Beenden](#terminate)|Wird aufgerufen, um das Worker-Objekt zu initialisieren, nachdem alle Anfragen an übergeben wurden [Execute](#execute).|  
  
|TypeDef|Beschreibung|  
|-------------|-----------------|  
|["RequestType"](#requesttype)|Eine Typedef für den Typ der Arbeitsaufgabe, die durch die Workerklasse verarbeitet werden kann.|  
  
 Ein herkömmliches *Worker* Klasse sieht folgendermaßen aus:  
  
 [!code-cpp[NVC_ATL_Utilities&#137;](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **Vorhandene Implementierungen**  
  
 Diese Klassen werden diesem Prototyp entsprechen:  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Erhält die Anfragen aus dem Threadpool und übergibt sie an eine Worker-Objekt, das erstellt und für jede Anforderung zerstört wird.|  
  
 **Verwendung**  
  
 Diese Vorlagenparameter erwarten, dass die Klasse diese Prototyp entsprechen:  
  
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
 Die Arbeitsaufgabe verarbeitet werden. Die Arbeitsaufgabe wird mit den gleichen Typ wie `RequestType`.  
  
 `pvWorkerParam`  
 Benutzerdefinierter Parameter durch die Workerklasse zu verstehen. Auch an übergeben `WorkerArchetype::Initialize` und `Terminate`.  
  
 `pOverlapped`  
 Ein Zeiger auf die [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) Struktur verwendet, um die Warteschlange zu erstellen, auf welche Elemente eingereiht wurden.  
  
## <a name="initialize"></a>WorkerArchetype::Initialize
Wird aufgerufen, um das Worker-Objekt zu initialisieren, bevor Anforderungen an übergeben werden `WorkerArchetype::Execute`.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parameter  
 `pvParam`  
 Benutzerdefinierter Parameter durch die Workerklasse zu verstehen. Auch an übergeben `WorkerArchetype::Terminate` und `WorkerArchetype::Execute`.  
  
### <a name="return-value"></a>Rückgabewert  
 Zurückgeben **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
## <a name="requesttype"></a>WorkerArchetype::RequestType
Eine Typedef für den Typ der Arbeitsaufgabe, die durch die Workerklasse verarbeitet werden kann.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Typ muss verwendet werden, als der erste Parameter der `WorkerArchetype::Execute` muss der in und aus einem ULONG_PTR umgewandelt werden kann.  
  
## <a name="terminate"></a>WorkerArchetype::Terminate
Wird aufgerufen, um das Worker-Objekt zu initialisieren, nachdem alle Anfragen an übergeben wurden `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parameter  
 `pvParam`  
 Benutzerdefinierter Parameter durch die Workerklasse zu verstehen. Auch an übergeben `WorkerArchetype::Initialize` und `WorkerArchetype::Execute`.  
  
## <a name="see-also"></a>Siehe auch  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)




