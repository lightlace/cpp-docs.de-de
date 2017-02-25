---
title: "CDCRenderTarget-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CDCRenderTarget"
  - "CDCRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDCRenderTarget-Klasse"
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CDCRenderTarget-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1DCRenderTarget".  
  
## Syntax  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDCRenderTarget::CDCRenderTarget](../Topic/CDCRenderTarget::CDCRenderTarget.md)|Erstellt ein CDCRenderTarget\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDCRenderTarget::Attach](../Topic/CDCRenderTarget::Attach.md)|Hängt die vorhandene Renderingzielschnittstelle an das Objekt an|  
|[CDCRenderTarget::BindDC](../Topic/CDCRenderTarget::BindDC.md)|Bindet das Renderingziel an den Gerätekontext, an den es Zeichenbefehle ausgibt|  
|[CDCRenderTarget::Create](../Topic/CDCRenderTarget::Create.md)|Erstellt einen CDCRenderTarget.|  
|[CDCRenderTarget::Detach](../Topic/CDCRenderTarget::Detach.md)|Trennt die Renderingzielschnittstelle vom Objekt|  
|[CDCRenderTarget::GetDCRenderTarget](../Topic/CDCRenderTarget::GetDCRenderTarget.md)|Gibt die ID2D1DCRenderTarget\-Schnittstelle zurück|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget\*](../Topic/CDCRenderTarget::operator%20ID2D1DCRenderTarget*.md)|Gibt die ID2D1DCRenderTarget\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDCRenderTarget::m\_pDCRenderTarget](../Topic/CDCRenderTarget::m_pDCRenderTarget.md)|Ein Zeiger auf ein ID2D1DCRenderTarget\-Objekt.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)