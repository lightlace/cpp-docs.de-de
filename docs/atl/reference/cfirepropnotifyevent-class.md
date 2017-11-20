---
title: CFirePropNotifyEvent Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs: C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4bcc9926974f9a61e951c15bca9af168eadab435
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent-Klasse
Diese Klasse stellt Methoden für die Benachrichtigung des Containers Senke bezüglich eigenschaftenänderungen Steuerelement bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Statisch) Benachrichtigt den Container-Ereignissenke, die eine Steuerelementeigenschaft geändert wurde.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Statisch) Benachrichtigt die Container-Senke, die eine Steuerelementeigenschaft ändern.|  
  
## <a name="remarks"></a>Hinweise  
 `CFirePropNotifyEvent`verfügt über zwei Methoden, mit die des Containers Senke, die eine Steuerelementeigenschaft geändert wurde oder benachrichtigt zu ändern.  
  
 Wenn die Klasse zur Implementierung des Steuerelements abgeleitet ist `IPropertyNotifySink`, `CFirePropNotifyEvent` Methoden werden aufgerufen, wenn Sie aufrufen `FireOnRequestEdit` oder `FireOnChanged`. Wenn die Steuerelementklasse nicht abgeleitet ist `IPropertyNotifySink`, Aufrufe dieser Funktionen zurückgeben `S_OK`.  
  
 Weitere Informationen zum Erstellen von Steuerelementen finden Sie unter der [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="fireonchanged"></a>CFirePropNotifyEvent::FireOnChanged  
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
  
##  <a name="fireonrequestedit"></a>CFirePropNotifyEvent::FireOnRequestEdit  
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
