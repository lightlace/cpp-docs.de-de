---
title: "IPointerInactiveImpl Class"
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
  - "IPointerInactiveImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inactive objects"
  - "IPointerInactive ATL implementation"
  - "IPointerInactiveImpl class"
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# IPointerInactiveImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und die [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712)\-Schnittstellenmethoden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IPointerInactiveImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IPointerInactiveImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](../Topic/IPointerInactiveImpl::GetActivationPolicy.md)|Ruft die aktuelle Aktivierungsrichtlinie für das Objekt ab.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](../Topic/IPointerInactiveImpl::OnInactiveMouseMove.md)|Benachrichtigt das Objekt, für das der Mauszeiger sich über die bewegt hat und das Objekt angegeben, kann Mausereignisse auslösen.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](../Topic/IPointerInactiveImpl::OnInactiveSetCursor.md)|Legt den Mauszeiger für das inaktive Objekt fest.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
  
## Hinweise  
 Ein inaktives Objekt ist eines, das einfach oder Ausführen geladen wird.  Anders als ein aktives Objekt kann ein inaktives Objekt Windows\-Maus\- und \-Tastaturmeldungen nicht erhalten.  Daher verwenden inaktive Objekte weniger Ressourcen und sind in der Regel effizienter.  
  
 Die [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712)\-Schnittstelle können Objekte, um eine minimale Ebene der Mausinteraktion beim Bleiben zu unterstützen inaktiv.  Diese Funktionalität ist für Steuerelemente besonders nützlich.  
  
 `IPointerInactiveImpl`\-Klasse implementiert die `IPointerInactive`\-Methoden, indem Sie einfach **E\_NOTIMPL** zurückgibt.  Allerdings implementiert sie **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds senden.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)