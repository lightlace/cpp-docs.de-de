---
title: IPropertyNotifySinkCP Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs: C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa15ef6706010154151c696eca320d464cdfee6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 `IPropertyNotifySinkCP`erbt alle Methoden über seine Basisklasse [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 Die [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) Schnittstelle einer Senke Objekt Gelegenheit zu dem Benachrichtigungen zum Ändern von Eigenschaften zu erhalten. Klasse `IPropertyNotifySinkCP` dieser Schnittstelle als Ausgangsschnittstelle auf ein verbindungsfähiges Objekt zur Verfügung gestellt. Der Client muss implementieren die `IPropertyNotifySink` Methoden für die Senke.  
  
 Leiten Sie eine Klasse von `IPropertyNotifySinkCP` sollen einen Verbindungspunkt zu erstellen, das darstellt die `IPropertyNotifySink` Schnittstelle.  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPointImpl-Klasse](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl-Klasse](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
