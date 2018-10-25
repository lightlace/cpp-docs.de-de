---
title: AgileEventSource-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
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
ms.openlocfilehash: 0f2ee187087917220751155cc43e8619e6dcf763
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054573"
---
# <a name="agileeventsource-class"></a>AgileEventSource-Klasse

Stellt ein Ereignis, das von einem agile-Komponente ausgelöst wird, wird eine Komponente, die von jedem Thread aus zugegriffen werden kann. Erbt von [EventSource](eventsource-class.md) und überschreibt die `Add` Memberfunktion mit einem weiteren Typ-Parameter zum Angeben von Optionen für das agile-Ereignis aufrufen.

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

## <a name="parameters"></a>Parameter

*TDelegateInterface*<br/>
Die Schnittstelle, ein Delegat, der einen Ereignishandler darstellt.

*TEventSourceOptions*<br/>
Ein [InvokeModeOptions](invokemodeoptions-structure.md) Struktur, deren Feld InvokeMode NA hodnotu nastaven `InvokeMode::StopOnFirstError` oder `InvokeMode::FireAll`.

## <a name="remarks"></a>Hinweise

Die große Mehrheit der Komponenten in der Windows-Runtime handelt es sich um agile-Komponenten. Weitere Informationen finden Sie unter [Threading und Marshalling (C++ / CX)](../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`EventSource`

`AgileEventSource`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[AgileEventSource::Add-Methode](#add)|Fügt den agile-Ereignishandler durch die Schnittstelle für die angegebenen Delegaten dargestellt wird, auf den Satz von Ereignishandlern für die aktuelle **AgileEventSource** Objekt.|

## <a name="add"></a> AgileEventSource::Add-Methode

Fügt den Ereignishandler, die durch die Schnittstelle für die angegebenen Delegaten dargestellt wird, auf den Satz von Ereignishandlern für die aktuelle [EventSource](eventsource-class.md) Objekt.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parameter

*delegateInterface*<br/>
Die Schnittstelle an ein Delegatobjekt, das einen Ereignishandler darstellt.

*token*<br/>
Wenn dieser Vorgang abgeschlossen ist, ein Handle, das das Ereignis darstellt. Verwenden Sie dieses Token als Parameter an die `Remove()` Methode, um den Ereignishandler zu verwerfen.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)