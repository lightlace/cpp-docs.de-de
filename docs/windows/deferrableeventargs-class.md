---
title: DeferrableEventArgs-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20cb959727cb2c515bd82d5b4d5d8e45019c6875
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788486"
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
[Deferrableeventargs:: Getdeferral](#getdeferral)             | Ruft einen Verweis auf die [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, das ein zurückgestelltes Ereignis darstellt.
[Deferrableeventargs:: Invokeallfinished](#invokeallfinished) | Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.

## <a name="remarks"></a>Hinweise

Instanzen dieser Klasse werden an die Ereignishandler für zurückgestellte Ereignisse übergeben. Der Vorlagenparameter stellt eine Schnittstelle, die die Details der Ereignisargumente für einen bestimmten Typ eines zurückgestellten Ereignisses definiert, und eine Klasse dar, die diese Schnittstelle implementiert.

Die Klasse wird als erstes Argument in einem Ereignishandler für ein zurückgestelltes Ereignis angezeigt. Rufen Sie die [GetDeferral](#getdeferral) -Methode zum Abrufen der [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt aus dem Sie alle Informationen über das zurückgestellte Ereignis erhalten. Wenn die Ereignisbehandlung abgeschlossen ist, müssen Sie „Complete“ für das Deferral-Objekt aufrufen. Rufen Sie dann [InvokeAllFinished](#invokeallfinished) am Ende der Ereignishandlermethode, die sicherstellt, dass es sich bei der Abschluss aller zurückgestellten Ereignisse ordnungsgemäß übermittelt wird.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="getdeferral"></a>Deferrableeventargs:: Getdeferral

Ruft einen Verweis auf die [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, das ein zurückgestelltes Ereignis darstellt.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```

### <a name="parameters"></a>Parameter

*Ergebnis*<br/>
Ein Zeiger, der auf die [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, wenn der Aufruf abgeschlossen ist.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="invokeallfinished"></a>Deferrableeventargs:: Invokeallfinished

Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.
  
```cpp
void InvokeAllFinished()  
```
  
### <a name="remarks"></a>Hinweise

Sie sollten diese Methode aufrufen, nach dem Aufrufen der Quelle Ereignis [InvokeAll](../windows/eventsource-invokeall-method.md). Das Aufrufen dieser Methode verhindert weitere Verzögerungen und erzwingt die Ausführung des Abschlusshandlers, wenn keine Verzögerungen ausgeführt wurden.
