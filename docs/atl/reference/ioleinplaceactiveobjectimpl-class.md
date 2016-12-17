---
title: "IOleInPlaceActiveObjectImpl Class"
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
  - "IOleInPlaceActiveObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], communication between container and control"
  - "IOleInPlaceActiveObject, ATL-Implementierung"
  - "IOleInPlaceActiveObjectImpl class"
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
caps.latest.revision: 22
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IOleInPlaceActiveObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zur Sicherung von Kommunikation zwischen einem direkten Steuerelement und dessen Container bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceActiveObjectImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IOleInPlaceActiveObjectImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](../Topic/IOleInPlaceActiveObjectImpl::ContextSensitiveHelp.md)|Aktiviert kontextbezogene Hilfe.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](../Topic/IOleInPlaceActiveObjectImpl::EnableModeless.md)|Ermöglicht nicht modale Dialogfelder.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IOleInPlaceActiveObjectImpl::GetWindow](../Topic/IOleInPlaceActiveObjectImpl::GetWindow.md)|Ruft einen Fensterhandle ab.|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnDocWindowActivate.md)|Benachrichtigt das Steuerelement, wenn das Dokumentfenster des Containers aktiviert oder deaktiviert ist.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](../Topic/IOleInPlaceActiveObjectImpl::OnFrameWindowActivate.md)|Benachrichtigt das Steuerelement, wenn das Rahmenfenster des Containers der obersten Ebene aktiviert oder deaktiviert ist.  Die ATL\-Implementierungsrückgaben|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](../Topic/IOleInPlaceActiveObjectImpl::ResizeBorder.md)|Informiert das Steuerelement, das es seine Rahmen Größe ändern muss.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](../Topic/IOleInPlaceActiveObjectImpl::TranslateAccelerator.md)|Verarbeitet Menüzugriffstastenmeldungen vom Container.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
  
## Hinweise  
 Die [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299)\-Schnittstelle können direkte Kommunikation zwischen einem Steuerelement und dessen Container; beispielsweise den aktiven Zustand des Steuerelements und des Containers hervorgeht und das Steuerelement informierend muss sie ihre Größe ändern.  \- Klasse `IOleInPlaceActiveObjectImpl` stellt eine Standardimplementierung von `IOleInPlaceActiveObject` und unterstützt **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)