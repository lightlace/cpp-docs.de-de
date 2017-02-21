---
title: "IConnectionPointImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IConnectionPointImpl"
  - "IConnectionPointImpl"
  - "ATL::IConnectionPointImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verbindungspunkte [C++], Implementieren"
  - "IConnectionPointImpl class"
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# IConnectionPointImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert einen Verbindungspunkt.  
  
## Syntax  
  
```  
  
      template<  
   class T,  
   const IID* piid,  
   class CDV = CComDynamicUnkArray   
>  
class ATL_NO_VTABLE IConnectionPointImpl :  
   public _ICPLocator< piid >  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IConnectionPointImpl`.  
  
 `piid`  
 Ein Zeiger auf IID der Schnittstelle dargestellt durch das Verbindungspunktobjekt.  
  
 `CDV`  
 Eine Klasse, die die Verbindungen verwaltet.  Der Standardwert ist [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), der unbegrenzte Verbindungen zulässig.  Sie können [CComUnkArray](../../atl/reference/ccomunkarray-class.md) auch verwenden, das eine feste Anzahl von Verbindungen angibt.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](../Topic/IConnectionPointImpl::Advise.md)|Richtet eine Verbindung zwischen dem Verbindungspunkt und einer Senke ein.|  
|[IConnectionPointImpl::EnumConnections](../Topic/IConnectionPointImpl::EnumConnections.md)|Erstellt einen Enumerator, um die Verbindungen für den Verbindungspunkt zu durchlaufen.|  
|[IConnectionPointImpl::GetConnectionInterface](../Topic/IConnectionPointImpl::GetConnectionInterface.md)|Ruft die IID der Schnittstelle ab, die durch den Verbindungspunkt dargestellt wird.|  
|[IConnectionPointImpl::GetConnectionPointContainer](../Topic/IConnectionPointImpl::GetConnectionPointContainer.md)|Ruft einen Schnittstellenzeiger zum verbindungsfähigen Objekt ab.|  
|[IConnectionPointImpl::Unadvise](../Topic/IConnectionPointImpl::Unadvise.md)|Beendet eine Verbindung, die zuvor durch `Advise` eingerichtet wird.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[IConnectionPointImpl::m\_vec](../Topic/IConnectionPointImpl::m_vec.md)|Verwaltet die Verbindungen für den Verbindungspunkt.|  
  
## Hinweise  
 `IConnectionPointImpl` implementiert einen Verbindungspunkt, der einem Objekt können, um eine Ausgangsschnittstelle dem Client verfügbar zu machen.  Der Client implementiert diese Schnittstelle in einem Objekt, das eine Senke aufgerufen wird.  
  
 ATL verwendet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md), um das verbindungsfähige Objekt zu implementieren.  Jeder Verbindungspunkt verbindungsfähigen innerhalb des Objekts stellt eine Ausgangsschnittstelle dar, die durch `piid`.  \- Klasse  *CDV* verwaltet die Verbindungen zwischen dem Verbindungspunkt und einer Senke.  Jede Verbindung wird identifiziert eindeutig durch eine "Cookie".  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## Vererbungshierarchie  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Class Overview](../../atl/atl-class-overview.md)