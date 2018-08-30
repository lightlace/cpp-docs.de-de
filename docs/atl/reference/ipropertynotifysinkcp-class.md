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
ms.openlocfilehash: 3fddd187dd6df58c4013b9c1fc7a08d5f644a0db
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203162"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP-Klasse
Diese Klasse stellt [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Schnittstelle als Ausgangsschnittstelle auf einem verbindungsfähigen Objekt.  
  
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
  
 Die [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) Schnittstelle ermöglicht es einem Senkenobjekts zum Empfangen von Benachrichtigungen über eigenschaftsänderungen. Klasse `IPropertyNotifySinkCP` macht diese Schnittstelle als Ausgangsschnittstelle auf einem verbindungsfähigen Objekt verfügbar. Der Client implementieren muss die `IPropertyNotifySink` Methoden für die Senke.  
  
 Leiten Sie eine Klasse von `IPropertyNotifySinkCP` Wenn Sie einen Verbindungspunkt erstellen, das darstellt möchten die `IPropertyNotifySink` Schnittstelle.  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPointImpl-Klasse](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl-Klasse](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
