---
title: "CBitmapRenderTarget Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CBitmapRenderTarget"
  - "CBitmapRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmapRenderTarget-Klasse"
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CBitmapRenderTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1BitmapRenderTarget".  
  
## Syntax  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](../Topic/CBitmapRenderTarget::CBitmapRenderTarget.md)|Erstellt ein CBitmapRenderTarget\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CBitmapRenderTarget::Attach](../Topic/CBitmapRenderTarget::Attach.md)|Hängt die vorhandene Renderingzielschnittstelle an das Objekt an|  
|[CBitmapRenderTarget::Detach](../Topic/CBitmapRenderTarget::Detach.md)|Trennt die Renderingzielschnittstelle vom Objekt|  
|[CBitmapRenderTarget::GetBitmap](../Topic/CBitmapRenderTarget::GetBitmap.md)|Ruft die Bitmap für dieses Renderingziel ab.  Die zurückgegebene Bitmap kann für Zeichenvorgänge verwendet werden.|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](../Topic/CBitmapRenderTarget::GetBitmapRenderTarget.md)|Gibt die ID2D1BitmapRenderTarget\-Schnittstelle zurück|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget\*](../Topic/CBitmapRenderTarget::operator%20ID2D1BitmapRenderTarget*.md)|Gibt die ID2D1BitmapRenderTarget\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CBitmapRenderTarget::m\_pBitmapRenderTarget](../Topic/CBitmapRenderTarget::m_pBitmapRenderTarget.md)|Ein Zeiger auf ein ID2D1BitmapRenderTarget\-Objekt.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CBitmapRenderTarget](../../mfc/reference/cbitmaprendertarget-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)