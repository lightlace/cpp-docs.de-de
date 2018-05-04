---
title: IPropertyNotifySinkCP Klasse | Microsoft Docs
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
ms.openlocfilehash: d9612cf65479e474b9a6e89a8f5a57ca078c9ed0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP-Klasse
Diese Klasse macht [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) -Schnittstelle als eine Ausgangsschnittstelle auf ein verbindungsfähiges Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IPropertyNotifySinkCP`.  
  
 `CDV`  
 Eine Klasse, die Verbindungen zwischen einem Verbindungspunkt und seine senken verwaltet. Der Standardwert ist [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), womit unbegrenzte Verbindungen. Sie können auch [CComUnkArray](../../atl/reference/ccomunkarray-class.md), die eine feste Anzahl von Verbindungen angibt.  
  
## <a name="remarks"></a>Hinweise  
 `IPropertyNotifySinkCP` erbt alle Methoden über seine Basisklasse [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 Die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstelle einer Senke Objekt Gelegenheit zu dem Benachrichtigungen zum Ändern von Eigenschaften zu erhalten. Klasse `IPropertyNotifySinkCP` dieser Schnittstelle als Ausgangsschnittstelle auf ein verbindungsfähiges Objekt zur Verfügung gestellt. Der Client muss implementieren die `IPropertyNotifySink` Methoden für die Senke.  
  
 Leiten Sie eine Klasse von `IPropertyNotifySinkCP` sollen einen Verbindungspunkt zu erstellen, das darstellt die `IPropertyNotifySink` Schnittstelle.  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPointImpl-Klasse](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl-Klasse](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
