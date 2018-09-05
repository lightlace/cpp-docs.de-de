---
title: CFirePropNotifyEvent-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88c816fecf71b94d25ac676f8169eeb26a2982fc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760216"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent-Klasse

Diese Klasse stellt Methoden für die Benachrichtigung des Containers-Senke in Bezug auf Änderungen von Steuerelement-Eigenschaften.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Statisch) Benachrichtigt den Container-Senke, die eine Steuerelementeigenschaft geändert wurde.|
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Statisch) Benachrichtigt den Container-Senke, die eine Steuerelementeigenschaft geändert wird.|

## <a name="remarks"></a>Hinweise

`CFirePropNotifyEvent` verfügt über zwei Methoden, mit die des Containers Senke benachrichtigt werden, die eine Steuerelementeigenschaft geändert hat oder zu ändern.

Wenn die Klasse implementiert das Steuerelement abgeleitet wird `IPropertyNotifySink`, `CFirePropNotifyEvent` Methoden werden aufgerufen, wenn Sie aufrufen `FireOnRequestEdit` oder `FireOnChanged`. Wenn eine Klasse nicht abgeleitet ist `IPropertyNotifySink`, Aufrufe dieser Funktionen gibt S_OK zurück.

Weitere Informationen zum Erstellen von Steuerelementen finden Sie unter den [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged

Benachrichtigt alle verbundenen [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Schnittstellen (auf jeder Verbindungspunkt des Objekts), die die Eigenschaft des angegebenen Objekts geändert wurde.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parameter

*pUnk*  
[in] Zeiger auf die `IUnknown` des Objekts, das die Benachrichtigung gesendet.

*dispID*  
[in] Der Bezeichner der Eigenschaft, die geändert wurde.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Diese Funktion ist sicher aufgerufen werden, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.

##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit

Benachrichtigt alle verbundenen [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Schnittstellen (auf jeder Verbindungspunkt des Objekts), die die angegebene geändert wird.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parameter

*pUnk*  
[in] Zeiger auf die `IUnknown` des Objekts, das die Benachrichtigung gesendet.

*dispID*  
[in] Der Bezeichner der Eigenschaft zu ändern.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Diese Funktion ist sicher aufgerufen werden, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
