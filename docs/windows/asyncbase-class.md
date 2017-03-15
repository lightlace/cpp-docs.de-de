---
title: "AsyncBase-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncBase-Klasse"
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implementiert den asynchronen Zustandsautomaten Windows\-Runtime.  
  
## Syntax  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase< TComplete, Details::Nil, resultType >;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase< TComplete, Details::Nil, resultType > : public Microsoft::WRL::Implements< IAsyncInfo >;  
```  
  
#### Parameter  
 `TComplete`  
 Ein Ereignishandler, der aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen wird.  
  
 `TProgress`  
 Ein Ereignishandler, der aufgerufen wird, wenn ein ausgeführter asynchroner Vorgang über den aktuellen Status der Operation angezeigt.  
  
 `resultType`  
 Einer der Enumerationswerte. [AsyncResultType](../windows/asyncresulttype-enumeration.md) Standardmäßig SingleResult.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[AsyncBase::AsyncBase\-Konstruktor](../windows/asyncbase-asyncbase-constructor.md)|Initialisiert eine Instanz der AsyncBase\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[AsyncBase::Cancel\-Methode](../windows/asyncbase-cancel-method.md)|Bricht einen asynchronen Vorgang ab.|  
|[AsyncBase::Close\-Methode](../windows/asyncbase-close-method.md)|Schließt den asynchronen Vorgang.|  
|[AsyncBase::FireCompletion\-Methode](../windows/asyncbase-firecompletion-method.md)|Ruft den Abschlussereignishandler auf oder legt den internen Statusdelegaten zurück.|  
|[AsyncBase::FireProgress\-Methode](../windows/asyncbase-fireprogress-method.md)|Ruft den aktuellen Statusereignishandler auf.|  
|[AsyncBase::get\_ErrorCode\-Methode](../windows/asyncbase-get-errorcode-method.md)|Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.|  
|[AsyncBase::get\_Id\-Methode](../windows/asyncbase-get-id-method.md)|Ruft das Handle des asynchronen Vorgangs ab.|  
|[AsyncBase::get\_Status\-Methode](../windows/asyncbase-get-status-method.md)|Ruft einen Wert ab, der den Status des asynchronen Vorgangs angibt.|  
|[AsyncBase::GetOnComplete\-Methode](../windows/asyncbase-getoncomplete-method.md)|Kopiert die Adresse des aktuellen Abschlussereignishandlers der angegebenen Variable.|  
|[AsyncBase::GetOnProgress\-Methode](../windows/asyncbase-getonprogress-method.md)|Kopiert die Adresse des aktuellen Statusereignishandlers der angegebenen Variable.|  
|[AsyncBase::put\_Id\-Methode](../windows/asyncbase-put-id-method.md)|Legt das Handle des asynchronen Vorgangs fest.|  
|[AsyncBase::PutOnComplete\-Methode](../windows/asyncbase-putoncomplete-method.md)|Legt die Adresse des Abschlussereignishandlers auf den angegebenen Wert festgelegt.|  
|[AsyncBase::PutOnProgress\-Methode](../windows/asyncbase-putonprogress-method.md)|Legt die Adresse des Statusereignishandlers auf den angegebenen Wert festgelegt.|  
|[AsyncBase::Start\-Methode](../windows/asyncbase-start-method.md)|Startet den asynchronen Vorgang.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[AsyncBase::CheckValidStateForDelegateCall\-Methode](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|Testet, ob Delegateigenschaften im aktuellen asynchronen Zustand geändert werden können.|  
|[AsyncBase::CheckValidStateForResultsCall\-Methode](../windows/asyncbase-checkvalidstateforresultscall-method.md)|Testet, ob die Ergebnisse eines asynchronen Vorgangs im aktuellen asynchronen Zustand erfasst werden können.|  
|[AsyncBase::ContinueAsyncOperation\-Methode](../windows/asyncbase-continueasyncoperation-method.md)|Bestimmt, ob die asynchrone Operation mit der Verarbeitung fortzufahren sollte oder sollte enthalten.|  
|[AsyncBase::CurrentStatus\-Methode](../windows/asyncbase-currentstatus-method.md)|Ruft den Status des aktuellen asynchronen Vorgangs ab.|  
|[AsyncBase::ErrorCode\-Methode](../windows/asyncbase-errorcode-method.md)|Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.|  
|[AsyncBase::OnCancel\-Methode](../windows/asyncbase-oncancel-method.md)|Wenn Sie in einer abgeleiteten Klasse, Löschen ein asynchroner Vorgang überschrieben werden.|  
|[AsyncBase::OnClose\-Methode](../windows/asyncbase-onclose-method.md)|Wenn Sie in einer abgeleiteten Klasse überschrieben werden, enthält einen asynchronen Vorgang.|  
|[AsyncBase::OnStart\-Methode](../windows/asyncbase-onstart-method.md)|Wenn Sie in einer abgeleiteten Klasse, beginnt ein asynchroner Vorgang überschrieben werden.|  
|[AsyncBase::TryTransitionToCompleted\-Methode](../windows/asyncbase-trytransitiontocompleted-method.md)|Gibt an, ob der aktuelle asynchrone Operation abgeschlossen wurde.|  
|[AsyncBase::TryTransitionToError\-Methode](../windows/asyncbase-trytransitiontoerror-method.md)|Gibt an, ob der angegebene Fehlercode den Zustand des internen Fehlers ändern kann.|  
  
## Vererbungshierarchie  
 `AsyncBase`  
  
 `AsyncBase`  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)