---
title: IVirtualProcessorRoot-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
dev_langs:
- C++
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a385bc12d3add9dd445243794135083c7cc1b3c1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot-Struktur
Eine Abstraktion für einen Hardwarethread, auf dem ein Threadproxy ausgeführt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IVirtualProcessorRoot : public IExecutionResource;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IVirtualProcessorRoot::Activate](#activate)|Bewirkt, dass die Ausführung Context-Schnittstelle zugeordneten Threadproxy `pContext` starten auf diesem virtuellen Prozessorstamm ausgeführt.|  
|[IVirtualProcessorRoot::Deactivate](#deactivate)|Bewirkt, dass den Threadproxy, der derzeit ausgeführten auf diesem virtuellen Prozessorstamm zu beenden, verteilen den Ausführungskontext. Der Threadproxy wird fortgesetzt, die bei einem Aufruf von Ausführen der `Activate` Methode.|  
|[IVirtualProcessorRoot::EnsureAllTasksVisible](#ensurealltasksvisible)|Bewirkt, dass Daten in der gesamten Speicherhierarchie der einzelnen Prozessoren für alle Prozessoren im System sichtbar werden. Dadurch wird sichergestellt, dass eine vollständige Arbeitsspeicher-Fence auf allen Prozessoren ausgeführt wurde, bevor die Methode zurückgegeben.|  
|[IVirtualProcessorRoot::GetId](#getid)|Gibt einen eindeutigen Bezeichner für den virtuellen Prozessorstamm zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Jeder virtuelle Prozessorstamm hat eine zugeordnete Ausführungsressource. Die `IVirtualProcessorRoot` Schnittstelle erbt von der [IExecutionResource](iexecutionresource-structure.md) Schnittstelle. Mehrere Stämme für virtuelle Prozessoren können der gleichen Hardwarethread des zugrunde liegenden entsprechen.  
  
 Der Ressourcen-Manager gewährt Stämme virtueller Prozessoren für Planer, die als Antwort auf Anforderungen von Ressourcen. Ein Planer können einen virtuellen Prozessorstamm Arbeiten ausführen, indem Sie es mit einem Ausführungskontext aktivieren.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IExecutionResource](iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="activate"></a>  IVirtualProcessorRoot:: Activate-Methode  
 Bewirkt, dass die Ausführung Context-Schnittstelle zugeordneten Threadproxy `pContext` starten auf diesem virtuellen Prozessorstamm ausgeführt.  
  
```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Eine Schnittstelle zum Ausführungskontext, der auf diesem virtuellen Prozessorstamm verteilt wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager wird einen Threadproxy bereit, wenn keine Ausführung Context-Schnittstelle zugeordnet ist `pContext`  
  
 Die `Activate` Methode kann verwendet werden, um die Ausführung der Arbeit auf einem neuen virtuellen Prozessorstamm zurückgegeben, der Ressourcen-Manager gestartet oder den Threadproxy auf einem virtuellen Prozessorstamm fortsetzen, die deaktiviert wurde oder zu deaktivieren. Finden Sie unter [IVirtualProcessorRoot:: Deactivate](#deactivate) für Weitere Informationen zur Deaktivierung. Wenn Sie einen deaktivierten virtuellen Prozessorstamm, der Parameter fortsetzen sind `pContext` muss als Parameter verwendet, um die virtuellen Prozessorstamm deaktivieren identisch sein.  
  
 Sobald ein virtueller Prozessorstamm zum ersten Mal, nachfolgende Paare von Aufrufen an aktiviert wurde `Deactivate` und `Activate` möglicherweise Rennen miteinander. Dies bedeutet, dass es akzeptabel für den Ressourcen-Manager zum Empfangen von eines Aufrufs von `Activate` vor dem Empfang der `Deactivate` Aufruf er vorgesehen war.  
  
 Wenn Sie einen virtuellen Prozessorstamm aktivieren, signalisieren, dass diese virtuellen Prozessorstamm Arbeit momentan ausgelastet ist, zum Ressourcen-Manager. Der Planer alle auf diesem Stamm auszuführende Arbeit gefunden, es wird erwartet zum Aufrufen der `Deactivate` Methode der Ressourcen-Manager zu informieren, dass der virtuelle Prozessorstamm im Leerlauf befindet. Der Ressourcen-Manager verwendet diese Daten für den Lastenausgleich des Systems an.  
  
 `invalid_argument` wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.  
  
 `invalid_operation` wird ausgelöst, wenn das Argument `pContext` stellt den Ausführungskontext, der von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde keine dar.  
  
 Die Aktivierung von einem virtuellen Prozessorstamm Abonnementebene des zugrunde liegenden Hardwarethreads wird um eins erhöht. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="deactivate"></a>  IVirtualProcessorRoot:: Deactivate-Methode  
 Bewirkt, dass den Threadproxy, der derzeit ausgeführten auf diesem virtuellen Prozessorstamm zu beenden, verteilen den Ausführungskontext. Der Threadproxy wird fortgesetzt, die bei einem Aufruf von Ausführen der `Activate` Methode.  
  
```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Kontext, der gerade von diesem Stamm weitergeleitet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert. Der Wert `true` gibt an, dass der Threadproxy von zurückgegeben der `Deactivate` Methode als Reaktion auf einen Aufruf der `Activate` Methode. Der Wert `false` gibt an, dass der Threadproxy von der Methode als Reaktion auf ein Benachrichtigungsereignis im Ressourcen-Manager zurückgegeben. Auf einem im Benutzermodus planbare (UMS) Threadplaner bedeutet dies, dass Elemente in der Vervollständigungsliste für den Planer wurden und der Planer erforderlich ist, zu deren Behandlung.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, einen virtuellen Prozessorstamm ausgeführt, wenn Sie keine Arbeit im Planer findet vorübergehend zu beenden. Ein Aufruf der `Deactivate` Methode muss innerhalb von stammen die `Dispatch` Methode des Ausführungskontexts, die der virtuelle Prozessorstamm zuletzt aktiviert wurde. In anderen Worten: der Threadproxy Aufrufen der `Deactivate` Methode muss das Projekt, das gerade auf dem virtuellen Prozessorstamm ausgeführt wird. Aufrufen der Methode auf einem virtuellen Prozessorstamm, während, dem Sie auf nicht ausgeführt werden, könnte zu nicht definiertem Verhalten führen.  
  
 Ein deaktivierter virtueller Prozessorstamm kann mit einem Aufruf von reaktiviert werden die `Activate` Methode mit dem gleichen Argument, die zum Übergeben der `Deactivate` Methode. Der Planer ist dafür verantwortlich sicherzustellen, dass Aufrufe der `Activate` und `Deactivate` Methoden kombiniert werden, aber sie sind nicht erforderlich, um in einer bestimmten Reihenfolge empfangen werden. Der Ressourcen-Manager kann einen Aufruf verarbeiten die `Activate` -Methode auf, bevor er einen Aufruf empfängt die `Deactivate` Methode, die er vorgesehen war.  
  
 Wenn ein virtueller Prozessorstamm aktiviert und der Rückgabewert der `Deactivate` Methode ist der Wert `false`, der Planer die UMS-Vervollständigungsliste über Abfragen sollte die `IUMSCompletionList::GetUnblockNotifications` Methode, wirken sich auf diese Informationen, und rufen Sie anschließend die anschließend`Deactivate`-Methode erneut. Dies sollte wiederholt werden, solange die `Deactivate` -Methode gibt den Wert `true`.  
  
 `invalid_argument` wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.  
  
 `invalid_operation` wird ausgelöst, wenn der virtuelle Prozessorstamm noch nie aktiviert wurde, oder das Argument `pContext` stellt den Ausführungskontext, der von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde keine dar.  
  
 Das Deaktivieren von einem virtuellen Prozessorstamm wird das Abonnement Maß an den Hardwarethread des zugrunde liegenden um eins verringert. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="ensurealltasksvisible"></a>  IVirtualProcessorRoot:: EnsureAllTasksVisible-Methode  
 Bewirkt, dass Daten in der gesamten Speicherhierarchie der einzelnen Prozessoren für alle Prozessoren im System sichtbar werden. Dadurch wird sichergestellt, dass eine vollständige Arbeitsspeicher-Fence auf allen Prozessoren ausgeführt wurde, bevor die Methode zurückgegeben.  
  
```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Kontext, der derzeit von diesem virtuellen Prozessorstamm weitergeleitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Sie können hilfreich sein diese Methode bei der Deaktivierung von einem virtuellen Prozessorstamm durch das Hinzufügen neuer Anwendungen in der Planer synchronisiert werden soll. Aus Gründen der Leistung können Sie entscheiden, zu dem Planer Arbeitsaufgaben hinzuzufügen, ohne eine Arbeitsspeicherbarriere, d. h., Arbeitselemente, die durch einen Thread für die Ausführung auf einem Prozessor hinzugefügt nicht sofort für alle anderen Prozessoren sichtbar sind. Mit dieser Methode in Verbindung mit der `Deactivate` Stämme Methode können Sie sicherstellen, dass der Planer seinen virtuellen Prozessor nicht aktiviert ist, auch von Arbeitselementen im des Planers Sammlungen vorhanden sind.  
  
 Ein Aufruf der `EnsureAllTasksVisibleThe` Methode muss innerhalb von stammen die `Dispatch` Methode des Ausführungskontexts, die der virtuelle Prozessorstamm zuletzt aktiviert wurde. In anderen Worten: der Threadproxy Aufrufen der `EnsureAllTasksVisible` Methode muss das Projekt, das gerade auf dem virtuellen Prozessorstamm ausgeführt wird. Aufrufen der Methode auf einem virtuellen Prozessorstamm, während, dem Sie auf nicht ausgeführt werden, könnte zu nicht definiertem Verhalten führen.  
  
 `invalid_argument` wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.  
  
 `invalid_operation` wird ausgelöst, wenn der virtuelle Prozessorstamm noch nie aktiviert wurde, oder das Argument `pContext` stellt den Ausführungskontext, der von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde keine dar.  
  
##  <a name="getid"></a>  IVirtualProcessorRoot:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den virtuellen Prozessorstamm zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganzzahlige Bezeichner.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
