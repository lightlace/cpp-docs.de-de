---
title: "IOleInPlaceObjectWindowlessImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IOleInPlaceObjectWindowlessImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activation [C++], ATL"
  - "ActiveX-Steuerelemente [C++], communication between container and control"
  - "Steuerelemente [ATL], windowless"
  - "deactivating ATL"
  - "IOleInPlaceObjectWindowless, ATL-Implementierung"
  - "IOleInPlaceObjectWindowlessImpl class"
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IOleInPlaceObjectWindowlessImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und stellt Methoden bereit, die ein fensterloses Steuerelement, um Fenstermeldungen zu empfangen und an den Drag & Drop\-Operationen teilnehmen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceObjectWindowlessImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IOleInPlaceObjectWindowlessImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](../Topic/IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp.md)|Aktiviert kontextbezogene Hilfe.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](../Topic/IOleInPlaceObjectWindowlessImpl::GetDropTarget.md)|Stellt die `IDropTarget`\-Schnittstelle direkt für ein ausgewähltes Objekt, fensterloses, das Drag & Drop unterstützt.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](../Topic/IOleInPlaceObjectWindowlessImpl::GetWindow.md)|Ruft einen Fensterhandle ab.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate.md)|Deaktiviert ein aktives Steuerelement direkt.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](../Topic/IOleInPlaceObjectWindowlessImpl::OnWindowMessage.md)|Stellt eine Nachricht vom Container an einem fensterlose Steuerelement aus, das direkt aktiviert ist.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](../Topic/IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo.md)|Ist ein zuvor deaktiviertes Steuerelement.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](../Topic/IOleInPlaceObjectWindowlessImpl::SetObjectRects.md)|Gibt an, welcher Teil des direkten Steuerelements sichtbar ist.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::UIDeactivate.md)|Deaktiviert und entfernt die Benutzeroberfläche, die direkte Aktivierung unterstützt.|  
  
## Hinweise  
 Die [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646)\-Schnittstelle verwaltet die Reaktivierung und die Deactivate direkter Steuerelemente und bestimmt, wie viel des Steuerelements sichtbar sein soll.  Die Schnittstelle ermöglicht [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) ein fensterloses Steuerelement, um Fenstermeldungen zu empfangen und an den Drag & Drop\-Operationen teilnehmen.  \- Klasse `IOleInPlaceObjectWindowlessImpl` stellt eine Standardimplementierung von `IOleInPlaceObject` und von `IOleInPlaceObjectWindowless` und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)