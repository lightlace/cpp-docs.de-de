---
title: "CD2DBitmapBrush-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DBitmapBrush"
  - "afxrendertarget/CD2DBitmapBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmapBrush-Klasse"
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DBitmapBrush-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1BitmapBrush".  
  
## Syntax  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](../Topic/CD2DBitmapBrush::CD2DBitmapBrush.md)|Überladen.  Erstellt von Datei ein CD2DBitmapBrush\-Objekt.|  
|[CD2DBitmapBrush::~CD2DBitmapBrush](../Topic/CD2DBitmapBrush::~CD2DBitmapBrush.md)|Der Destruktor.  Wird aufgerufen, wenn ein D2D\-Bitmappinselobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](../Topic/CD2DBitmapBrush::Attach.md)|Hängt die vorhandene Ressourcenschnittstelle an das Objekt an|  
|[CD2DBitmapBrush::Create](../Topic/CD2DBitmapBrush::Create.md)|Erstellt einen CD2DBitmapBrush.  \(Überschreibt [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DBitmapBrush::Destroy](../Topic/CD2DBitmapBrush::Destroy.md)|Zerstört ein CD2DBitmapBrush\-Objekt.  \(Überschreibt [CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md).\)|  
|[CD2DBitmapBrush::Detach](../Topic/CD2DBitmapBrush::Detach.md)|Trennt die Ressourcenschnittstelle vom Objekt|  
|[CD2DBitmapBrush::Get](../Topic/CD2DBitmapBrush::Get.md)|Gibt eine ID2D1BitmapBrush\-Schnittstelle zurück|  
|[CD2DBitmapBrush::GetBitmap](../Topic/CD2DBitmapBrush::GetBitmap.md)|Ruft die Bitmapquelle ab, mit der dieser Pinsel zeichnet|  
|[CD2DBitmapBrush::GetExtendModeX](../Topic/CD2DBitmapBrush::GetExtendModeX.md)|Ruft die Methode ab, durch die der Pinsel jene Bereiche, die seine Bitmap überschreiten, nebeneinander anordnet|  
|[CD2DBitmapBrush::GetExtendModeY](../Topic/CD2DBitmapBrush::GetExtendModeY.md)|Ruft die Methode ab, durch die der Pinsel jene Bereiche, die seine Bitmap überschreiten, untereinander anordnet|  
|[CD2DBitmapBrush::GetInterpolationMode](../Topic/CD2DBitmapBrush::GetInterpolationMode.md)|Ruft die Interpolationsmethode ab, die verwendet wird, wenn die Pinselbitmap skaliert wird oder gedreht wird|  
|[CD2DBitmapBrush::SetBitmap](../Topic/CD2DBitmapBrush::SetBitmap.md)|Gibt die Bitmapquelle an, mit der dieser Pinsel zeichnet|  
|[CD2DBitmapBrush::SetExtendModeX](../Topic/CD2DBitmapBrush::SetExtendModeX.md)|Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen, nebeneinander anordnet|  
|[CD2DBitmapBrush::SetExtendModeY](../Topic/CD2DBitmapBrush::SetExtendModeY.md)|Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen, untereinander anordnet|  
|[CD2DBitmapBrush::SetInterpolationMode](../Topic/CD2DBitmapBrush::SetInterpolationMode.md)|Gibt den verwendeten Interpolationsmodus an, wenn die Pinselbitmap skaliert wird oder gedreht wird|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](../Topic/CD2DBitmapBrush::CommonInit.md)|Initialisiert das Objekt|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush\*](../Topic/CD2DBitmapBrush::operator%20ID2D1BitmapBrush*.md)|Gibt eine ID2D1BitmapBrush\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DBitmapBrush::m\_pBitmap](../Topic/CD2DBitmapBrush::m_pBitmap.md)|Speichert einen Zeiger auf ein CD2DBitmap\-Objekt.|  
|[CD2DBitmapBrush::m\_pBitmapBrush](../Topic/CD2DBitmapBrush::m_pBitmapBrush.md)|Speichert einen Zeiger auf ein ID2D1BitmapBrush\-Objekt.|  
|[CD2DBitmapBrush::m\_pBitmapBrushProperties](../Topic/CD2DBitmapBrush::m_pBitmapBrushProperties.md)|Bitmappinseleigenschaften.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DBitmapBrush](../../mfc/reference/cd2dbitmapbrush-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)