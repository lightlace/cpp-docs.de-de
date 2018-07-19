---
title: IPropertyNotifySinkCP-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66fd7b267a70b962bb5c28bb5835bd96d44a92f0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879188"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP-Klasse
Diese Klasse stellt [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstelle als Ausgangsschnittstelle auf einem verbindungsfähigen Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IPropertyNotifySinkCP`.  
  
 *CDV*  
 Eine Klasse, die Verbindungen zwischen einem Verbindungspunkt und die senken verwaltet. Der Standardwert ist [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), womit unbegrenzte Verbindungen. Sie können auch [CComUnkArray](../../atl/reference/ccomunkarray-class.md), die eine feste Anzahl von Verbindungen angibt.  
  
## <a name="remarks"></a>Hinweise  
 `IPropertyNotifySinkCP` erbt alle Methoden über seine Basisklasse, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 Die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstelle ermöglicht es einem Senkenobjekts zum Empfangen von Benachrichtigungen über eigenschaftsänderungen. Klasse `IPropertyNotifySinkCP` macht diese Schnittstelle als Ausgangsschnittstelle auf einem verbindungsfähigen Objekt verfügbar. Der Client implementieren muss die `IPropertyNotifySink` Methoden für die Senke.  
  
 Leiten Sie eine Klasse von `IPropertyNotifySinkCP` Wenn Sie einen Verbindungspunkt erstellen, das darstellt möchten die `IPropertyNotifySink` Schnittstelle.  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPointImpl-Klasse](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl-Klasse](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
