---
title: "IQuickActivateImpl Class"
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
  - "ATL::IQuickActivateImpl"
  - "ATL::IQuickActivateImpl<T>"
  - "ATL.IQuickActivateImpl"
  - "ATL.IQuickActivateImpl<T>"
  - "IQuickActivateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activating ATL controls"
  - "Steuerelemente [ATL], Aktivieren"
  - "IQuickActivate ATL implementation"
  - "IQuickActivateImpl class"
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IQuickActivateImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse kombiniert Initialisierung der Container Steuerin einen einzelnen Aufruf.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template<   
class T   
>  
class ATL_NO_VTABLE IQuickActivateImpl :  
public IQuickActivate  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IQuickActivateImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](../Topic/IQuickActivateImpl::GetContentExtent.md)|Ruft die aktuelle Anzeigengröße für ein aktives Steuerelement ab.|  
|[IQuickActivateImpl::QuickActivate](../Topic/IQuickActivateImpl::QuickActivate.md)|Führt eine schnelle Initialisierung von Steuerelementen aus, die geladen werden.|  
|[IQuickActivateImpl::SetContentExtent](../Topic/IQuickActivateImpl::SetContentExtent.md)|Informiert das steuern, wie viel Bildbereich der Container zugewiesen wurde.|  
  
## Hinweise  
 Die [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146)\-Schnittstellenhilfecontainer vermeiden Verzögerungen beim Laden von Steuerelementen, indem sie Initialisierung in einem einzelnen Aufruf kombinieren.  Die `QuickActivate`\-Methode ermöglicht es dem Container, um einen Zeiger auf eine Struktur [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) zu übergeben, die Zeiger auf allen Schnittstellen die Steuerelement enthält.  Bei Rückgabe unterstützen die geht einen Zeiger auf eine Struktur [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721), die Zeiger zu den eigenen Schnittstellen enthält, die vom Container verwendet werden.  \- Klasse `IQuickActivateImpl` stellt eine Standardimplementierung von **IQuickActivate** und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)