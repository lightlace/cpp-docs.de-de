---
title: "IObjectWithSiteImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl<T>"
  - "IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl"
  - "ATL::IObjectWithSiteImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IObjectWithSiteImpl class"
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# IObjectWithSiteImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Methoden, die einem Objekt ermöglichen, um mit der Site zu kommunizieren.  
  
## Syntax  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IObjectWithSiteImpl :  
   public IObjectWithSite  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IObjectWithSiteImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](../Topic/IObjectWithSiteImpl::GetSite.md)|Fragt die Site für einen Schnittstellenzeiger ab.|  
|[IObjectWithSiteImpl::SetChildSite](../Topic/IObjectWithSiteImpl::SetChildSite.md)|Stellt das Objekt mit dem **IUnknown**  Zeiger der Site.|  
|[IObjectWithSiteImpl::SetSite](../Topic/IObjectWithSiteImpl::SetSite.md)|Stellt das Objekt mit dem **IUnknown** Zeiger der Site.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m\_spUnkSite](../Topic/IObjectWithSiteImpl::m_spUnkSite.md)|Verwaltet den **IUnknown** Zeiger der Site.|  
  
## Hinweise  
 Die [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765)\-Schnittstelle können Objekte, um die Site zu kommunizieren.  \- Klasse `IObjectWithSiteImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 `IObjectWithSiteImpl` gibt zwei Methoden.  Die Clientersten erhalte `SetSite`, den **IUnknown** Zeiger der Site.  Dieser Zeiger wird innerhalb des Objekts gespeichert und kann durch einen Aufruf `GetSite` später abgerufen werden.  
  
 In der Regel leiten Sie die Klasse von `IObjectWithSiteImpl`, wenn Sie ein Objekt erstellen, das kein \- Steuerelement ist.  Bei Steuerelementen leiten Sie die Klasse von [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), die auch einen Sitezeiger bereitstellt.  Leiten Sie die Klasse von `IObjectWithSiteImpl` und von `IOleObjectImpl`.  
  
## Vererbungshierarchie  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)