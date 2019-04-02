---
title: DeferrableEventArgs-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 4a3786e65873d6837389ad4fa5e7d06a14d66460
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785567"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs-Klasse

Eine für die Ereignisargumenttypen für Verzögerungen verwendete Vorlagenklasse.

## <a name="syntax"></a>Syntax

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>Parameter

*TEventArgsInterface*<br/>
Der Schnittstellentyp, der die Argumente für ein zurückgestelltes Ereignis deklariert.

*TEventArgsClass*<br/>
Implementiert die Klasse, *TEventArgsInterface*.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                         | Beschreibung
------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------
[DeferrableEventArgs::GetDeferral](#getdeferral)             | Ruft einen Verweis auf die [Verzögerung](/uwp/api/windows.foundation.deferral) Objekt, das ein zurückgestelltes Ereignis darstellt.
[DeferrableEventArgs::InvokeAllFinished](#invokeallfinished) | Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.

## <a name="remarks"></a>Hinweise

Instanzen dieser Klasse werden an die Ereignishandler für zurückgestellte Ereignisse übergeben. Der Vorlagenparameter stellt eine Schnittstelle, die die Details der Ereignisargumente für einen bestimmten Typ eines zurückgestellten Ereignisses definiert, und eine Klasse dar, die diese Schnittstelle implementiert.

Die Klasse wird als erstes Argument in einem Ereignishandler für ein zurückgestelltes Ereignis angezeigt. Rufen Sie die [GetDeferral](#getdeferral) -Methode zum Abrufen der [Verzögerung](/uwp/api/windows.foundation.deferral) Objekt aus dem Sie alle Informationen über das zurückgestellte Ereignis erhalten. Wenn die Ereignisbehandlung abgeschlossen ist, müssen Sie „Complete“ für das Deferral-Objekt aufrufen. Rufen Sie dann [InvokeAllFinished](#invokeallfinished) am Ende der Ereignishandlermethode, die sicherstellt, dass es sich bei der Abschluss aller zurückgestellten Ereignisse ordnungsgemäß übermittelt wird.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="getdeferral"></a>DeferrableEventArgs::GetDeferral

Ruft einen Verweis auf die [Verzögerung](/uwp/api/windows.foundation.deferral) Objekt, das ein zurückgestelltes Ereignis darstellt.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>Parameter

*result*<br/>
Ein Zeiger, der auf die [Verzögerung](/uwp/api/windows.foundation.deferral) Objekt, wenn der Aufruf abgeschlossen ist.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="invokeallfinished"></a>DeferrableEventArgs::InvokeAllFinished

Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>Hinweise

Sie sollten diese Methode aufrufen, nach dem Aufrufen der Quelle Ereignis [InvokeAll](eventsource-class.md#invokeall). Das Aufrufen dieser Methode verhindert weitere Verzögerungen und erzwingt die Ausführung des Abschlusshandlers, wenn keine Verzögerungen ausgeführt wurden.
