---
title: "IViewObjectExImpl Class"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::IViewObjectExImpl<T>"
  - "ATL.IViewObjectExImpl"
  - "ATL::IViewObjectExImpl"
  - "ATL.IViewObjectExImpl<T>"
  - "IViewObjectExImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], drawing"
  - "advise sinks"
  - "IViewObjectEx ATL implementation"
  - "IViewObjectExImpl class"
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IViewObjectExImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und stellt Standardimplementierungen der [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) und [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)\-Schnittstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IViewObjectExImpl :  
public IViewObjectEx  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IViewObjectExImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](../Topic/IViewObjectExImpl::Draw.md)|Zeichnet eine Darstellung des Steuerelements auf einen Gerätekontext.|  
|[IViewObjectExImpl::Freeze](../Topic/IViewObjectExImpl::Freeze.md)|Friert gezeichnete die Darstellung eines Steuerelements ändert ein, sodass es nicht so `Unfreeze`.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IViewObjectExImpl::GetAdvise](../Topic/IViewObjectExImpl::GetAdvise.md)|Ruft eine vorhandene Advise\-Senken\-Verbindung auf dem Steuerelement ab, wenn ein aktives gibt.|  
|[IViewObjectExImpl::GetColorSet](../Topic/IViewObjectExImpl::GetColorSet.md)|Gibt die Logische Palette zurück, die vom Steuerelement zum Zeichnen verwendet wird.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IViewObjectExImpl::GetExtent](../Topic/IViewObjectExImpl::GetExtent.md)|Ruft die Anzeigengröße des Steuerelements in den HIMETRIC\-Einheiten \(0,01 mm pro Einheit\) vom Steuerelementklassendatenmember [CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md) ab.|  
|[IViewObjectExImpl::GetNaturalExtent](../Topic/IViewObjectExImpl::GetNaturalExtent.md)|Stellt Größenanpassungs\-Hinweise vom Container für das Objekt zur Verwendung bereit, wie der Benutzer die Größe ändert.|  
|[IViewObjectExImpl::GetRect](../Topic/IViewObjectExImpl::GetRect.md)|Gibt ein Rechteck zurück, das einen angeforderten zeichnenden Aspekt beschreibt.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IViewObjectExImpl::GetViewStatus](../Topic/IViewObjectExImpl::GetViewStatus.md)|EINGABETASTEinformationen über die Durchlässigkeit des Objekts und welche Zeichnungsaspekte unterstützt werden.|  
|[IViewObjectExImpl::QueryHitPoint](../Topic/IViewObjectExImpl::QueryHitPoint.md)|Überprüft, ob der angegebene Punkt im angegebenen Rechteck ist und einen [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187)\-Wert in `pHitResult` zurückgibt.|  
|[IViewObjectExImpl::QueryHitRect](../Topic/IViewObjectExImpl::QueryHitRect.md)|Überprüft, ob das Anzeigenrechteck des Steuerelements entweder sich Punkt im Rechteck der angegebenen Position schneidet und einen **HITRESULT** \-Wert in `pHitResult` zurückgibt.|  
|[IViewObjectExImpl::SetAdvise](../Topic/IViewObjectExImpl::SetAdvise.md)|Installieren eine Verbindung zwischen dem Steuerelement und einer Advise\-Senke, sodass die Senke zu Änderungen in der Ansicht des Steuerelements benachrichtigt werden.|  
|[IViewObjectExImpl::Unfreeze](../Topic/IViewObjectExImpl::Unfreeze.md)|Taut gezeichnete die Darstellung des Steuerelements.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
  
## Hinweise  
 Die [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318) und [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)\-Schnittstellen können ein Steuerelement, sich direkt anzuzeigen, und eine Advise\-Senke zu erstellen und zu verwalten, um den Container von Änderungen im Steuerelement zu benachrichtigen.  Die **IViewObjectEx**\-Schnittstelle unterstützt erweiterte Steuerelementfuntkionen wie flimmerfreie Zeichnungen, nicht rechteckige und transparente Steuerelemente und Treffertests \(beispielsweise, wie nahe ein Mausklick auf dem Steuerelement berücksichtigt werden sollen muss\).  \- Klasse `IViewObjectExImpl` stellt eine Standardimplementierung dieser Schnittstellen und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
## Vererbungshierarchie  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Lernprogramm](../../atl/active-template-library-atl-tutorial.md)   
 [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)   
 [Class Overview](../../atl/atl-class-overview.md)