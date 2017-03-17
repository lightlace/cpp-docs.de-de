---
title: Klasse CFirePropNotifyEvent | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 1511a9e9ba287d12aade7c393887c6b5f8880b96
ms.lasthandoff: 02/24/2017

---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent-Klasse
Diese Klasse stellt Methoden für die Benachrichtigung des Containers Senke in Bezug auf die Steuerelement-Eigenschaft ändert.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Statisch) Benachrichtigt den Container-Senke, die Eigenschaft eines Steuerelements geändert hat.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Statisch) Benachrichtigt den Container-Senke, die Eigenschaft eines Steuerelements zu ändern.|  
  
## <a name="remarks"></a>Hinweise  
 `CFirePropNotifyEvent`verfügt über zwei Methoden, die Senke für den Container zu benachrichtigen, dass die Eigenschaft eines Steuerelements geändert hat oder geändert wird.  
  
 Wenn die Klasse zur Implementierung des Steuerelements abgeleitet ist `IPropertyNotifySink`, `CFirePropNotifyEvent` Methoden werden aufgerufen, wenn Sie aufrufen `FireOnRequestEdit` oder `FireOnChanged`. Wenn eine Klasse nicht von abgeleitet ist `IPropertyNotifySink`, Aufrufe dieser Funktionen zurückgeben `S_OK`.  
  
 Weitere Informationen zum Erstellen von Steuerelementen finden Sie unter der [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="fireonchanged"></a>CFirePropNotifyEvent::FireOnChanged  
 Benachrichtigt alle verbundenen [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstellen (auf jedem Verbindungspunkt des Objekts), die die angegebene Objekt-Eigenschaft geändert wurde.  
  
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
 Benachrichtigt alle verbundenen [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstellen (auf jedem Verbindungspunkt des Objekts), die die angegebene Objekt-Eigenschaft geändert wird.  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Zeiger auf die **IUnknown** des Objekts, das die Benachrichtigung gesendet.  
  
 *dispID*  
 [in] Der Bezeichner der Eigenschaft zu ändern.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist sicher aufgerufen werden, auch wenn das Steuerelement Verbindungspunkte nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

