---
title: IVirtualProcessorRoot-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IVirtualProcessorRoot
dev_langs:
- C++
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 18
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: ca095a249ee0eb9e1393e232ab7957a7060a2002
ms.lasthandoff: 02/24/2017

---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot-Struktur
Eine Abstraktion für einen Hardwarethread, auf dem ein Threadproxy ausgeführt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IVirtualProcessorRoot : public IExecutionResource;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IVirtualProcessorRoot:: Activate-Methode](#activate)|Bewirkt, dass die Ausführung Context-Schnittstelle zugeordneten Threadproxy `pContext` starten auf diesem virtuellen Prozessorstamm ausgeführt.|  
|[IVirtualProcessorRoot:: Deactivate-Methode](#deactivate)|Bewirkt, dass den Threadproxy auf diesem virtuellen Prozessorstamm so beenden Sie den Ausführungskontext verteilen. Der Threadproxy wird fortgesetzt, bei einem Aufruf von Ausführen der `Activate` Methode.|  
|[IVirtualProcessorRoot:: EnsureAllTasksVisible-Methode](#ensurealltasksvisible)|Bewirkt, dass Daten in der Speicherhierarchie der einzelnen Prozessoren für alle Prozessoren auf dem System sichtbar werden. Dadurch wird sichergestellt, dass ein vollständige Arbeitsspeicher-Fence auf allen Prozessoren ausgeführt wurde, bevor die Methode zurückgegeben.|  
|[IVirtualProcessorRoot:: GetID-Methode](#getid)|Gibt einen eindeutigen Bezeichner für den virtuellen Prozessorstamm zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Jeder virtuelle Prozessorstamm hat eine zugeordnete Ausführungsressource. Die `IVirtualProcessorRoot` Schnittstelle erbt von der [IExecutionResource](iexecutionresource-structure.md) Schnittstelle. Mehrere virtuelle Prozessorstämme können den gleichen zugrunde liegenden Hardwarethread entsprechen.  
  
 Der Ressourcen-Manager gewährt Stämme virtueller Prozessoren Zeitplanungsmodulen in Reaktion auf Anfragen nach Ressourcen. Ein Planer können einen virtuellen Prozessorstamm Aufgaben durchführen, indem er mit einem Ausführungskontext aktivieren.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [IExecutionResource](iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameactivatea--ivirtualprocessorrootactivate-method"></a><a name="activate"></a>IVirtualProcessorRoot:: Activate-Methode  
 Bewirkt, dass die Ausführung Context-Schnittstelle zugeordneten Threadproxy `pContext` starten auf diesem virtuellen Prozessorstamm ausgeführt.  
  
```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Eine Schnittstelle zum Ausführungskontext, der auf diesem virtuellen Prozessorstamm weitergeleitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager wird einen Threadproxy bereit, wenn keine Ausführung Context-Schnittstelle zugeordnet ist`pContext`  
  
 Die `Activate` Methode kann verwendet werden, um zu beginnen, Arbeit auf einem neuen virtuellen Prozessorstamm vom Ressourcen-Manager zurückgegeben oder um den Threadproxy auf einem virtuellen Prozessorstamm fortzusetzen, der deaktiviert wurde oder zu deaktivieren. Finden Sie unter [IVirtualProcessorRoot:: Deactivate](#deactivate) für Weitere Informationen zur Deaktivierung. Wenn Sie einen deaktivierter virtueller Prozessorstamm, der Parameter fortsetzen werden `pContext` muss identisch mit den Parameter für den virtuellen Prozessorstamm zu deaktivieren.  
  
 Sobald ein virtueller Prozessorstamm zum ersten Mal, nachfolgende Paare Aufrufe aktiviert wurde `Deactivate` und `Activate` kann zwischen. Dies bedeutet, dass es für den Ressourcen-Manager einen Aufruf von zulässigen `Activate` vor dem Empfang der `Deactivate` Aufruf er vorgesehen war.  
  
 Wenn Sie einen virtuellen Prozessorstamm aktivieren, signalisieren, dass es sich bei diesem virtuellen Prozessorstamm derzeit mit der Arbeit beschäftigt ist, an den Ressourcen-Manager. Wenn der Planer keine Arbeit auf diesem Stamm ausgeführt findet, wird voraussichtlich Aufrufen der `Deactivate` -Methode informiert den Ressourcen-Manager, dass der virtuelle Prozessorstamm im Leerlauf befindet. Der Ressourcen-Manager verwendet diese Daten zum Lastenausgleich des Systems.  
  
 `invalid_argument`wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.  
  
 `invalid_operation`wird ausgelöst, wenn das Argument `pContext` nicht den Ausführungskontext darstellt, die von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde.  
  
 Aktivieren von einem virtuellen Prozessorstamm wird die Abonnementebene des zugrunde liegenden Hardwarethreads um eins erhöht. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="a-namedeactivatea--ivirtualprocessorrootdeactivate-method"></a><a name="deactivate"></a>IVirtualProcessorRoot:: Deactivate-Methode  
 Bewirkt, dass den Threadproxy auf diesem virtuellen Prozessorstamm so beenden Sie den Ausführungskontext verteilen. Der Threadproxy wird fortgesetzt, bei einem Aufruf von Ausführen der `Activate` Methode.  
  
```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Kontext, der gerade von diesem Stamm weitergeleitet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert. Der Wert `true` gibt an, dass der Threadproxy zurückgegeben der `Deactivate` -Methode als Reaktion auf einen Aufruf der `Activate` Methode. Der Wert `false` gibt an, dass der Threadproxy von der Methode als Reaktion auf ein Benachrichtigungsereignis im Ressourcen-Manager zurückgegeben. Auf einem im Benutzermodus planbare (UMS) Threadplaner bedeutet dies, dass Elemente in der Vervollständigungsliste des Planers wurden und der Planer erforderlich ist, um sie zu behandeln.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode auf um einen virtuellen Prozessorstamm ausgeführt, wenn Sie keine Arbeit im Planer findet vorübergehend zu beenden. Ein Aufruf der `Deactivate` Methode muss stammen aus der `Dispatch` Methode des Ausführungskontexts, die der virtuelle Prozessorstamm zuletzt aktiviert wurde. Das heißt, der Threadproxy Aufrufen der `Deactivate` -Methode muss derjenige sein, der gerade auf dem virtuellen Prozessorstamm ausgeführt wird. Aufrufen der Methode auf einem virtuellen Prozessorstamm, dem Sie nicht auf ausführen könnte zu nicht definiertem Verhalten führen.  
  
 Ein deaktivierter virtueller Prozessorstamm kann mit einem Aufruf von reaktiviert die `Activate` Methode mit demselben Argument, das an übergeben wurde die `Deactivate` Methode. Der Planer ist dafür verantwortlich sicherzustellen, dass Aufrufe der `Activate` und `Deactivate` Methoden kombiniert werden, aber sie sind nicht in einer bestimmten Reihenfolge empfangen werden müssen. Der Ressourcen-Manager kann einen Aufruf behandeln die `Activate` -Methode auf, bevor er einen Aufruf empfängt die `Deactivate` Methode, die er vorgesehen war.  
  
 Wenn ein virtueller Prozessorstamm aktiviert und der Rückgabewert der `Deactivate` Methode ist der Wert `false`, der Planer die UMS-Vervollständigungsliste über Abfragen sollte die `IUMSCompletionList::GetUnblockNotifications` -Methode diesen Informationen agieren, und anschließend rufen Sie dann die `Deactivate` -Methode erneut. Dies sollte wiederholt werden, bis zu der Zeit der `Deactivate` -Methode gibt den Wert `true`.  
  
 `invalid_argument`wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.  
  
 `invalid_operation`wird ausgelöst, wenn der virtuelle Prozessorstamm noch nie aktiviert wurde, oder das Argument `pContext` nicht den Ausführungskontext darstellt, die von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde.  
  
 Das Deaktivieren von einem virtuellen Prozessorstamm wird die Abonnementebene des zugrunde liegenden Hardwarethreads um eins verringert. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="a-nameensurealltasksvisiblea--ivirtualprocessorrootensurealltasksvisible-method"></a><a name="ensurealltasksvisible"></a>IVirtualProcessorRoot:: EnsureAllTasksVisible-Methode  
 Bewirkt, dass Daten in der Speicherhierarchie der einzelnen Prozessoren für alle Prozessoren auf dem System sichtbar werden. Dadurch wird sichergestellt, dass ein vollständige Arbeitsspeicher-Fence auf allen Prozessoren ausgeführt wurde, bevor die Methode zurückgegeben.  
  
```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Kontext, der gerade von diesem virtuellen Prozessorstamm weitergeleitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Möglicherweise finden Sie diese Methode nützlich bei der Deaktivierung von einem virtuellen Prozessorstamm mit der Hinzufügung neuer Arbeit zum Planer synchronisieren möchten. Aus Gründen der Leistung können Sie entscheiden, dem Planer Arbeitsaufgaben hinzuzufügen, ohne eine Arbeitsspeicherbarriere, d. h., Arbeitsaufgaben hinzugefügt, die von einem Thread auf einem Prozessor ausgeführt wurden, nicht sofort auf allen anderen Prozessoren sichtbar sind. Mit dieser Methode in Verbindung mit der `Deactivate` Methode können Sie sicherstellen, dass der Planer deaktivieren Sie alle seinen virtuellen Prozessor wird Stämme, während die Arbeitsaufgaben in den Planer Auflistungen vorhanden sind.  
  
 Ein Aufruf der `EnsureAllTasksVisibleThe` Methode muss stammen aus der `Dispatch` Methode des Ausführungskontexts, die der virtuelle Prozessorstamm zuletzt aktiviert wurde. Das heißt, der Threadproxy Aufrufen der `EnsureAllTasksVisible` -Methode muss derjenige sein, der gerade auf dem virtuellen Prozessorstamm ausgeführt wird. Aufrufen der Methode auf einem virtuellen Prozessorstamm, dem Sie nicht auf ausführen könnte zu nicht definiertem Verhalten führen.  
  
 `invalid_argument`wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.  
  
 `invalid_operation`wird ausgelöst, wenn der virtuelle Prozessorstamm noch nie aktiviert wurde, oder das Argument `pContext` nicht den Ausführungskontext darstellt, die von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde.  
  
##  <a name="a-namegetida--ivirtualprocessorrootgetid-method"></a><a name="getid"></a>IVirtualProcessorRoot:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den virtuellen Prozessorstamm zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganzzahlige Bezeichner.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

