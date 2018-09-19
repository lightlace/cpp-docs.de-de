---
title: DeferrableEventArgs-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a53e33d55ccfac7eff763e53240295ea9b7b2a1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600970"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs-Klasse

Eine für die Ereignisargumenttypen für Verzögerungen verwendete Vorlagenklasse.

## <a name="syntax"></a>Syntax

```cpp
template <
typename TEventArgsInterface,
typename TEventArgsClass
>
class DeferrableEventArgs : public TEventArgsInterface
```

### <a name="parameters"></a>Parameter

*TEventArgsInterface*  
Der Schnittstellentyp, der die Argumente für ein zurückgestelltes Ereignis deklariert.

*TEventArgsClass*  
Implementiert die Klasse, *TEventArgsInterface*.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[DeferrableEventArgs::GetDeferral-Methode](../windows/deferrableeventargs-getdeferral-method.md)|Ruft einen Verweis auf die [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, das ein zurückgestelltes Ereignis darstellt.|
|[DeferrableEventArgs::InvokeAllFinished-Methode](../windows/deferrableeventargs-invokeallfinished-method.md)|Wird aufgerufen, um anzugeben, dass das Behandeln eines zurückgestellten Ereignisses abgeschlossen ist.|

## <a name="remarks"></a>Hinweise

Instanzen dieser Klasse werden an die Ereignishandler für zurückgestellte Ereignisse übergeben. Der Vorlagenparameter stellt eine Schnittstelle, die die Details der Ereignisargumente für einen bestimmten Typ eines zurückgestellten Ereignisses definiert, und eine Klasse dar, die diese Schnittstelle implementiert.

Die Klasse wird als erstes Argument in einem Ereignishandler für ein zurückgestelltes Ereignis angezeigt. Rufen Sie die [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) -Methode zum Abrufen der [Verzögerung](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt aus dem Sie alle Informationen über das zurückgestellte Ereignis erhalten. Wenn die Ereignisbehandlung abgeschlossen ist, müssen Sie „Complete“ für das Deferral-Objekt aufrufen. Rufen Sie dann [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) am Ende der Ereignishandlermethode, die sicherstellt, dass es sich bei der Abschluss aller zurückgestellten Ereignisse ordnungsgemäß übermittelt wird.

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)