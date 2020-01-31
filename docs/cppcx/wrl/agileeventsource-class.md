---
title: Agileeventsource-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- AgileEventSource class
ms.openlocfilehash: fa1e0a72d865b2993e149f6e4d2b57fe13463a61
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821739"
---
# <a name="agileeventsource-class"></a>Agileeventsource-Klasse

Stellt ein Ereignis dar, das von einer Agile-Komponente ausgelöst wird. Hierbei handelt es sich um eine Komponente, auf die von jedem Thread aus zugegriffen werden kann. Erbt von [eventSource](eventsource-class.md) und überschreibt die `Add` Member-Funktion mit einem zusätzlichen Typparameter zum Angeben von Optionen für das Aufrufen des Agile-Ereignisses.

## <a name="syntax"></a>Syntax

```cpp
template<
    typename TDelegateInterface,
    typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>
>
class AgileEventSource :
    public Microsoft::WRL::EventSource<
        TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>Parameters

*TDelegateInterface*<br/>
Die-Schnittstelle zu einem Delegaten, der einen Ereignishandler darstellt.

*TEventSourceOptions*<br/>
Eine [invokemodeoptions](invokemodeoptions-structure.md) -Struktur, deren invokemode-Feld auf `InvokeMode::StopOnFirstError` oder `InvokeMode::FireAll`festgelegt ist.

## <a name="remarks"></a>Hinweise

Bei den meisten Komponenten in der Windows-Runtime handelt es sich um Agile-Komponenten. Weitere Informationen finden Sie unter [Threading und MarshallingC++(/CX)](../../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`EventSource`

`AgileEventSource`

## <a name="requirements"></a>-Anforderungen

**Header:** Event. h

**Namespace:** Microsoft::WRL

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|-Name|Beschreibung|
|----------|-----------------|
|[Agileeventsource:: Add-Methode](#add)|Fügt den von der angegebenen delegatschnittstelle dargestellten Agile-Ereignishandler an den Satz von Ereignis Handlern für das aktuelle **agileeventsource** -Objekt an.|

## <a name="add"></a>Agileeventsource:: Add-Methode

Fügt den Ereignishandler, der durch die angegebene delegatschnittstelle dargestellt wird, an den Satz von Ereignis Handlern für das aktuelle [eventSource](eventsource-class.md) -Objekt an.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parameters

*delegateInterface*<br/>
Die-Schnittstelle zu einem Delegatobjekt, das einen Ereignishandler darstellt.

*token*<br/>
Wenn dieser Vorgang abgeschlossen ist, ein Handle, das das Ereignis darstellt. Verwenden Sie dieses Token als Parameter für die `Remove()`-Methode, um den Ereignishandler zu verwerfen.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)