---
title: "CHwndRenderTarget-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CHwndRenderTarget"
  - "afxrendertarget/CHwndRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHwndRenderTarget-Klasse"
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CHwndRenderTarget-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1HwndRenderTarget".  
  
## Syntax  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](../Topic/CHwndRenderTarget::CHwndRenderTarget.md)|Erstellt ein CHwndRenderTarget\-Objekt aus HWND.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](../Topic/CHwndRenderTarget::Attach.md)|Hängt die vorhandene Renderingzielschnittstelle an das Objekt an|  
|[CHwndRenderTarget::CheckWindowState](../Topic/CHwndRenderTarget::CheckWindowState.md)|Gibt an, ob der diesem Renderingziel zugeordnete HWND okkludiert wird.|  
|[CHwndRenderTarget::Create](../Topic/CHwndRenderTarget::Create.md)|Erstellt ein dem Fenster zugeordnetes Renderingziel|  
|[CHwndRenderTarget::Detach](../Topic/CHwndRenderTarget::Detach.md)|Trennt die Renderingzielschnittstelle vom Objekt|  
|[CHwndRenderTarget::GetHwnd](../Topic/CHwndRenderTarget::GetHwnd.md)|Gibt das diesem Renderingziel zugeordnete HWND zurück.|  
|[CHwndRenderTarget::GetHwndRenderTarget](../Topic/CHwndRenderTarget::GetHwndRenderTarget.md)|Gibt die ID2D1HwndRenderTarget\-Schnittstelle zurück.|  
|[CHwndRenderTarget::ReCreate](../Topic/CHwndRenderTarget::ReCreate.md)|Erstellt ein dem Fenster zugeordnetes Renderingziel neu|  
|[CHwndRenderTarget::Resize](../Topic/CHwndRenderTarget::Resize.md)|Ändert die Größe des Renderingziels in die angegebene Pixelgröße|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget\*](../Topic/CHwndRenderTarget::operator%20ID2D1HwndRenderTarget*.md)|Gibt die ID2D1HwndRenderTarget\-Schnittstelle zurück.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CHwndRenderTarget::m\_pHwndRenderTarget](../Topic/CHwndRenderTarget::m_pHwndRenderTarget.md)|Ein Zeiger auf ein ID2D1HwndRenderTarget\-Objekt.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)