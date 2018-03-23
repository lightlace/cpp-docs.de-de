---
title: AgileEventSource Klasse | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- AgileEventSource class
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d025fc2be86fb5b59107d1deee39962c3c6db04
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="agileeventsource-class"></a>AgileEventSource-Klasse
Stellt ein agile-Ereignis. Erbt von [EventSource](eventsource-class.md) und überschreibt die `Add` Memberfunktion mit einem zusätzlichen Typs Parameter zum Angeben von Optionen für das Aufrufen des agile-Ereignisses.
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```  
  
#### <a name="parameters"></a>Parameter  
 `TDelegateInterface`  
 Die Schnittstelle, ein Delegat, der einen Ereignishandler darstellt.

 `TEventSourceOptions` Ein [InvokeModeOptions](invokemodeoptions-structure.md) Struktur, deren Feld InvokeMode `InvokeMode::StopOnFirstError` oder `InvokeMode::FireAll`.

## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AgileEventSource::Add-Methode](#add)|Fügt den agile-Ereignishandler, die durch die Schnittstelle des angegebenen Delegaten dargestellt wird, auf den Satz der Ereignishandler für das aktuelle AgileEventSource-Objekt.|  

## <a name="add"></a> AgileEventSource::Add-Methode

Fügt den Ereignishandler, die durch die Schnittstelle des angegebenen Delegaten dargestellt wird, auf den Satz der Ereignishandler für das aktuelle EventSource-Objekt.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);
```

### <a name="parameters"></a>Parameter

*delegateInterface*

Die Schnittstelle mit einem Delegatobjekt, der einen Ereignishandler darstellt.

*Token* Wenn dieser Vorgang abgeschlossen wird, ein Handle, das das Ereignis darstellt. Verwenden Sie dieses Token als Parameter an die Remove()-Methode, um den Ereignishandler zu verwerfen.

### <a name="return-value"></a>Rückgabewert
S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `EventSource`  
 `AgileEventSource`
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)