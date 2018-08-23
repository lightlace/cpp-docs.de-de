---
title: AsyncBase-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: cba5aaaec3303d9cd3534ff86cb677219c9c81c7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586783"
---
# <a name="asyncbase-class"></a>AsyncBase-Klasse

Implementiert den asynchronen Zustandsautomat der Windows-Runtime.

## <a name="syntax"></a>Syntax

```cpp
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

### <a name="parameters"></a>Parameter

*TComplete*  
Ein Ereignishandler, der aufgerufen wird, wenn ein asynchroner Vorgang abgeschlossen ist.

*TProgress*  
Ein Ereignishandler, der aufgerufen wird, wenn Sie ein aktiven asynchroner Vorgang, den aktuellen Status des Vorgangs meldet.

*ResultType-Element*  
Eines der [AsyncResultType](../windows/asyncresulttype-enumeration.md) -Enumerationswerte fest. In der Standardeinstellung `SingleResult`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[AsyncBase::AsyncBase-Konstruktor](../windows/asyncbase-asyncbase-constructor.md)|Initialisiert eine Instanz von der **AsyncBase** Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[AsyncBase::Cancel-Methode](../windows/asyncbase-cancel-method.md)|Bricht einen asynchronen Vorgang ab.|
|[AsyncBase::Close-Methode](../windows/asyncbase-close-method.md)|Schließt den asynchronen Vorgang an.|
|[AsyncBase::FireCompletion-Methode](../windows/asyncbase-firecompletion-method.md)|Ruft den Ereignishandler für den Abschluss, oder setzt den internen Status-Delegaten.|
|[AsyncBase::FireProgress-Methode](../windows/asyncbase-fireprogress-method.md)|Ruft den aktuellen Status-Ereignishandler.|
|[AsyncBase::get_ErrorCode-Methode](../windows/asyncbase-get-errorcode-method.md)|Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.|
|[AsyncBase::get_Id-Methode](../windows/asyncbase-get-id-method.md)|Ruft das Handle des asynchronen Vorgangs ab.|
|[AsyncBase::get_Status-Methode](../windows/asyncbase-get-status-method.md)|Ruft einen Wert, der den Status des asynchronen Vorgangs angibt.|
|[AsyncBase::GetOnComplete-Methode](../windows/asyncbase-getoncomplete-method.md)|Kopiert die Adresse des aktuellen ereignishandlers Abschluss an die angegebene Variable.|
|[AsyncBase::GetOnProgress-Methode](../windows/asyncbase-getonprogress-method.md)|Kopiert die Adresse des aktuellen ereignishandlers Status an die angegebene Variable.|
|[AsyncBase::put_Id-Methode](../windows/asyncbase-put-id-method.md)|Legt das Handle des asynchronen Vorgangs fest.|
|[AsyncBase::PutOnComplete-Methode](../windows/asyncbase-putoncomplete-method.md)|Legt die Adresse des ereignishandlers Abschluss auf den angegebenen Wert fest.|
|[AsyncBase::PutOnProgress-Methode](../windows/asyncbase-putonprogress-method.md)|Legt die Adresse des ereignishandlers Status mit dem angegebenen Wert fest.|
|[AsyncBase::Start-Methode](../windows/asyncbase-start-method.md)|Beginnt den asynchronen Vorgang an.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[AsyncBase::CheckValidStateForDelegateCall-Methode](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|Testet, ob in den aktuellen Status des asynchronen delegateigenschaften geändert werden können.|
|[AsyncBase::CheckValidStateForResultsCall-Methode](../windows/asyncbase-checkvalidstateforresultscall-method.md)|Testet, ob die Ergebnisse eines asynchronen Vorgangs in den aktuellen asynchronen Zustand erfasst werden können.|
|[AsyncBase::ContinueAsyncOperation-Methode](../windows/asyncbase-continueasyncoperation-method.md)|Bestimmt, ob der asynchrone Vorgang im Fortsetzen der Verarbeitung oder anhalten soll.|
|[AsyncBase::CurrentStatus-Methode](../windows/asyncbase-currentstatus-method.md)|Ruft den Status der aktuellen asynchronen Vorgang ab.|
|[AsyncBase::ErrorCode-Methode](../windows/asyncbase-errorcode-method.md)|Ruft den Fehlercode für den aktuellen asynchronen Vorgang ab.|
|[AsyncBase::OnCancel-Methode](../windows/asyncbase-oncancel-method.md)|Ruft beim Überschreiben in einer abgeleiteten Klasse Bricht einen asynchronen Vorgang ab.|
|[AsyncBase::OnClose-Methode](../windows/asyncbase-onclose-method.md)|Ruft beim Überschreiben in einer abgeleiteten Klasse schließt einen asynchronen Vorgang.|
|[AsyncBase::OnStart-Methode](../windows/asyncbase-onstart-method.md)|Ruft beim Überschreiben in einer abgeleiteten Klasse wird einen asynchronen Vorgang gestartet.|
|[AsyncBase::TryTransitionToCompleted-Methode](../windows/asyncbase-trytransitiontocompleted-method.md)|Gibt an, ob der aktuelle asynchrone Vorgang abgeschlossen wurde.|
|[AsyncBase::TryTransitionToError-Methode](../windows/asyncbase-trytransitiontoerror-method.md)|Gibt an, ob der angegebene Fehlercode auf den internen Fehlerzustand ändern kann.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)