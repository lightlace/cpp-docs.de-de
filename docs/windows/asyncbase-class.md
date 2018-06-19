---
title: AsyncBase-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
dev_langs:
- C++
helpviewer_keywords:
- AsyncBase class
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c9dbd5d7296edaed9e850e6453f1b1b593ddba9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863386"
---
# <a name="asyncbase-class"></a>AsyncBase-Klasse
Implementiert den asynchronen Zustandsautomat der Windows-Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase<TComplete, Details::Nil, resultType> : public Microsoft::WRL::Implements<IAsyncInfo>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `TComplete`  
 Ein Ereignishandler, der beim Abschluss eines asynchronen Vorgangs aufgerufen wird.  
  
 `TProgress`  
 Ein Ereignishandler, der aufgerufen wird, wenn ein asynchrones ausgeführten Vorgangs meldet, das den aktuellen Status des Vorgangs.  
  
 `resultType`  
 Eines der [AsyncResultType](../windows/asyncresulttype-enumeration.md) Enumerationswerte. Standardmäßig SingleResult.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AsyncBase::AsyncBase-Konstruktor](../windows/asyncbase-asyncbase-constructor.md)|Initialisiert eine Instanz der AsyncBase-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AsyncBase::Cancel-Methode](../windows/asyncbase-cancel-method.md)|Bricht einen asynchronen Vorgang ab.|  
|[AsyncBase::Close-Methode](../windows/asyncbase-close-method.md)|Schließt den asynchronen Vorgang an.|  
|[AsyncBase::FireCompletion-Methode](../windows/asyncbase-firecompletion-method.md)|Wird der Ereignishandler für den Abschluss des Vorgangs aufgerufen, oder setzt den internen Status Delegaten zurück.|  
|[AsyncBase::FireProgress-Methode](../windows/asyncbase-fireprogress-method.md)|Wird der aktuelle Fortschritt-Ereignishandler aufgerufen.|  
|[AsyncBase::get_ErrorCode-Methode](../windows/asyncbase-get-errorcode-method.md)|Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.|  
|[AsyncBase::get_Id-Methode](../windows/asyncbase-get-id-method.md)|Ruft das Handle des asynchronen Vorgangs ab.|  
|[AsyncBase::get_Status-Methode](../windows/asyncbase-get-status-method.md)|Ruft einen Wert, der den Status des asynchronen Vorgangs angibt.|  
|[AsyncBase::GetOnComplete-Methode](../windows/asyncbase-getoncomplete-method.md)|Kopiert die Adresse des aktuellen ereignishandlers Abschluss der angegebenen Variablen.|  
|[AsyncBase::GetOnProgress-Methode](../windows/asyncbase-getonprogress-method.md)|Kopiert die Adresse des aktuellen ereignishandlers Status der angegebenen Variablen.|  
|[AsyncBase::put_Id-Methode](../windows/asyncbase-put-id-method.md)|Legt das Handle des asynchronen Vorgangs fest.|  
|[AsyncBase::PutOnComplete-Methode](../windows/asyncbase-putoncomplete-method.md)|Legt die Adresse des ereignishandlers Abschluss auf den angegebenen Wert fest.|  
|[AsyncBase::PutOnProgress-Methode](../windows/asyncbase-putonprogress-method.md)|Legt die Adresse des ereignishandlers Status mit dem angegebenen Wert fest.|  
|[AsyncBase::Start-Methode](../windows/asyncbase-start-method.md)|Beginnt den asynchronen Vorgang an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AsyncBase::CheckValidStateForDelegateCall-Methode](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|Testet, ob in den aktuellen Status des asynchronen delegateigenschaften geändert werden können.|  
|[AsyncBase::CheckValidStateForResultsCall-Methode](../windows/asyncbase-checkvalidstateforresultscall-method.md)|Testet, ob die Ergebnisse eines asynchronen Vorgangs in den aktuellen Status des asynchronen gesammelt werden können.|  
|[AsyncBase::ContinueAsyncOperation-Methode](../windows/asyncbase-continueasyncoperation-method.md)|Bestimmt, ob der asynchrone Vorgang der Verarbeitung fortsetzen oder Anhalten sollte.|  
|[AsyncBase::CurrentStatus-Methode](../windows/asyncbase-currentstatus-method.md)|Ruft den Status der aktuellen asynchronen Vorgang ab.|  
|[AsyncBase::ErrorCode-Methode](../windows/asyncbase-errorcode-method.md)|Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.|  
|[AsyncBase::OnCancel-Methode](../windows/asyncbase-oncancel-method.md)|Ruft beim Überschreiben in einer abgeleiteten Klasse Bricht einen asynchronen Vorgang ab.|  
|[AsyncBase::OnClose-Methode](../windows/asyncbase-onclose-method.md)|Ruft beim Überschreiben in einer abgeleiteten Klasse schließt einen asynchronen Vorgang.|  
|[AsyncBase::OnStart-Methode](../windows/asyncbase-onstart-method.md)|Ruft beim Überschreiben in einer abgeleiteten Klasse startet einen asynchronen Vorgang.|  
|[AsyncBase::TryTransitionToCompleted-Methode](../windows/asyncbase-trytransitiontocompleted-method.md)|Gibt an, ob die aktuelle asynchrone Vorgang abgeschlossen ist.|  
|[AsyncBase::TryTransitionToError-Methode](../windows/asyncbase-trytransitiontoerror-method.md)|Gibt an, ob der angegebene Fehlercode Zustand "Interner Fehler" ändern kann.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `AsyncBase`  
  
 `AsyncBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)