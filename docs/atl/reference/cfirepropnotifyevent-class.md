---
title: CFirePropNotifyEvent Klasse | Microsoft Docs
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
ms.openlocfilehash: 728f4e973a7ef74dcdbb44150375df235e0d990e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent-Klasse
Diese Klasse stellt Methoden für die Benachrichtigung des Containers Senke bezüglich eigenschaftenänderungen Steuerelement bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Statisch) Benachrichtigt den Container-Ereignissenke, die eine Steuerelementeigenschaft geändert wurde.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Statisch) Benachrichtigt die Container-Senke, die eine Steuerelementeigenschaft ändern.|  
  
## <a name="remarks"></a>Hinweise  
 `CFirePropNotifyEvent` verfügt über zwei Methoden, mit die des Containers Senke, die eine Steuerelementeigenschaft geändert wurde oder benachrichtigt zu ändern.  
  
 Wenn die Klasse zur Implementierung des Steuerelements abgeleitet ist `IPropertyNotifySink`, `CFirePropNotifyEvent` Methoden werden aufgerufen, wenn Sie aufrufen `FireOnRequestEdit` oder `FireOnChanged`. Wenn die Steuerelementklasse nicht abgeleitet ist `IPropertyNotifySink`, Aufrufe dieser Funktionen zurückgeben `S_OK`.  
  
 Weitere Informationen zum Erstellen von Steuerelementen finden Sie unter der [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged  
 Benachrichtigt alle verbundenen [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstellen (auf jeden Verbindungspunkt des Objekts), die die angegebene Objekt-Eigenschaft geändert wurde.  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Zeiger auf die **IUnknown** des Objekts, das die Benachrichtigung gesendet.  
  
 *dispID*  
 [in] Der Bezeichner der Eigenschaft, die geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist sicher aufgerufen werden, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.  
  
##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit  
 Benachrichtigt alle verbundenen [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstellen (auf jeden Verbindungspunkt des Objekts), die die angegebenen Objekteigenschaft ändern.  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Zeiger auf die **IUnknown** des Objekts, das die Benachrichtigung gesendet.  
  
 *dispID*  
 [in] Der Bezeichner für die Eigenschaft zu ändern.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist sicher aufgerufen werden, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
