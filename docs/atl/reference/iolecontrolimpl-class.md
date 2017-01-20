---
title: "IOleControlImpl Class"
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
  - "IOleControlImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOleControlImpl class"
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# IOleControlImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Standardimplementierung der Schnittstelle **IOleControl** und implementiert **IUnknown**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IOleControlImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IOleControlImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](../Topic/IOleControlImpl::FreezeEvents.md)|Gibt an, ob der Container Ereignisse vom Steuerelement ignoriert oder akzeptiert.|  
|[IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md)|Füllt Informationen über das gewünschte Tastaturverhalten des Steuerelements aus.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleControlImpl::OnAmbientPropertyChange](../Topic/IOleControlImpl::OnAmbientPropertyChange.md)|Informiert ein Steuerelement, dass eine oder mehrere der Ambient\-Eigenschaften des Containers geändert hat.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IOleControlImpl::OnMnemonic](../Topic/IOleControlImpl::OnMnemonic.md)|Informiert das Steuerelement, dass ein Benutzer eine angegebene Tastatureingabe gedrückt wurde.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
  
## Hinweise  
 \- Klasse `IOleControlImpl` stellt eine Standardimplementierung der Schnittstelle [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [IOleObjectImpl Class](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)