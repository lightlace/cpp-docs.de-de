---
title: AgileEventSource Klasse | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58eb96e3a0268d3ba70b60d9c315e935e19485f3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858119"
---
# <a name="agileeventsource-class"></a>AgileEventSource-Klasse

Stellt ein Ereignis, das von einer Komponente agile ausgelöst wird, eine Komponente, die von jedem Thread aus zugegriffen werden kann. Erbt von [EventSource](eventsource-class.md) und überschreibt die `Add` Memberfunktion mit einem zusätzlichen Typs Parameter zum Angeben von Optionen für das Aufrufen des agile-Ereignisses.

## <a name="syntax"></a>Syntax

```
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>Parameter  
 `TDelegateInterface`  

 Die Schnittstelle, ein Delegat, der einen Ereignishandler darstellt.

 `TEventSourceOptions`  
 Ein [InvokeModeOptions](invokemodeoptions-structure.md) Struktur, deren Feld InvokeMode `InvokeMode::StopOnFirstError` oder `InvokeMode::FireAll`.

## <a name="remarks"></a>Hinweise

Die meisten Komponenten in Windows-Runtime sind agilen Komponenten. Weitere Informationen finden Sie unter [Threading und Marshalling (C + c++ / CX)](../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

 `EventSource` `AgileEventSource`

## <a name="requirements"></a>Anforderungen

 **Header:** event.h

 **Namespace:** Microsoft::WRL

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[AgileEventSource::Add-Methode](#add)|Fügt den agile-Ereignishandler, die durch die Schnittstelle des angegebenen Delegaten dargestellt wird, auf den Satz der Ereignishandler für das aktuelle AgileEventSource-Objekt.|

## <a name="add"></a> AgileEventSource::Add-Methode

Fügt den Ereignishandler, die durch die Schnittstelle des angegebenen Delegaten dargestellt wird, auf den Satz der Ereignishandler für das aktuelle [EventSource](eventsource-class.md) Objekt.

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


## <a name="see-also"></a>Siehe auch

 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)
