---
title: "CDrawingManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDrawingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDrawingManager class"
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CDrawingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse implementiert `CDrawingManager` komplexe Zeichnungsalgorithmen.  
  
## Syntax  
  
```  
class CDrawingManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDrawingManager::CDrawingManager](../Topic/CDrawingManager::CDrawingManager.md)|Erstellt ein `CDrawingManager`\-Objekt.|  
|`CDrawingManager::~CDrawingManager`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap\_32](../Topic/CDrawingManager::CreateBitmap_32.md)|Erstellt eine 32\-Bit\-geräteunabhängigeBitmap \(DIBs\) diese Anwendungen kann direkt zu schreiben.|  
|[CDrawingManager::DrawAlpha](../Topic/CDrawingManager::DrawAlpha.md)|Zeigt Bitmaps an, die die transparenten oder halbtransparenten Pixel haben.|  
|[CDrawingManager::DrawRotated](../Topic/CDrawingManager::DrawRotated.md)|Dreht ein Inhalt des mit DC das angegebene Rechteck mit \+\/\- 90 Grad|  
|[CDrawingManager::DrawEllipse](../Topic/CDrawingManager::DrawEllipse.md)|Zeichnet eine Ellipse mit dem angegebenen Füllung und den Rahmenfarben.|  
|[CDrawingManager::DrawGradientRing](../Topic/CDrawingManager::DrawGradientRing.md)|Zeichnet einen Ring und füllt ihn mit einem Farbverlauf aus.|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](../Topic/CDrawingManager::DrawLine,%20CDrawingManager::DrawLineA.md)|Zeichnet eine Zeile.|  
|[CDrawingManager::DrawRect](../Topic/CDrawingManager::DrawRect.md)|Zeichnet ein Rechteck mit dem angegebenen Füllung und den Rahmenfarben.|  
|[CDrawingManager::DrawShadow](../Topic/CDrawingManager::DrawShadow.md)|Zeichnet einen Schatten für einen rechteckigen Bereich.|  
|[CDrawingManager::Fill4ColorsGradient](../Topic/CDrawingManager::Fill4ColorsGradient.md)|Füllt einen rechteckigen Bereich mit zwei Farbverläufen aus.|  
|[CDrawingManager::FillGradient](../Topic/CDrawingManager::FillGradient.md)|Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf aus.|  
|[CDrawingManager::FillGradient2](../Topic/CDrawingManager::FillGradient2.md)|Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf aus.  Die Richtung der Farbänderung des Farbverlaufs ist ebenfalls angegeben.|  
|[CDrawingManager::GrayRect](../Topic/CDrawingManager::GrayRect.md)|Füllt ein Rechteck mit einer angegebenen grauen Farbe aus.|  
|[CDrawingManager::HighlightRect](../Topic/CDrawingManager::HighlightRect.md)|Hebt einen rechteckigen Bereich hervor.|  
|[CDrawingManager::HLStoRGB\_ONE](../Topic/CDrawingManager::HLStoRGB_ONE.md)|Konvertiert eine Farbe aus einer HLS\-Darstellung auf eine RGB\-Darstellung.|  
|[CDrawingManager::HLStoRGB\_TWO](../Topic/CDrawingManager::HLStoRGB_TWO.md)|Konvertiert eine Farbe aus einer HLS\-Darstellung auf eine RGB\-Darstellung.|  
|[CDrawingManager::HSVtoRGB](../Topic/CDrawingManager::HSVtoRGB.md)|Konvertiert eine Farbe aus einer HSV\-Darstellung auf eine RGB\-Darstellung.|  
|[CDrawingManager::HuetoRGB](../Topic/CDrawingManager::HuetoRGB.md)|Hilfsmethode, die einen Farbtonwert zu einem roten konvertiert, Grün oder Blauanteil.|  
|[CDrawingManager::MirrorRect](../Topic/CDrawingManager::MirrorRect.md)|Kippt einen rechteckigen Bereich.|  
|[CDrawingManager::PixelAlpha](../Topic/CDrawingManager::PixelAlpha.md)|Hilfsmethode, die die endgültige Farbe für ein halbtransparentes Pixel bestimmt.|  
|[CDrawingManager::PrepareShadowMask](../Topic/CDrawingManager::PrepareShadowMask.md)|Erstellt eine Bitmap, die als Schatten verwendet werden kann.|  
|[CDrawingManager::RGBtoHSL](../Topic/CDrawingManager::RGBtoHSL.md)|Konvertiert eine Farbe aus einer RGB\-Darstellung zu einer HSL\-Darstellung.|  
|[CDrawingManager::RGBtoHSV](../Topic/CDrawingManager::RGBtoHSV.md)|Konvertiert eine Farbe aus einer RGB\-Darstellung zu einer HSV\-Darstellung.|  
|[CDrawingManager::SetAlphaPixel](../Topic/CDrawingManager::SetAlphaPixel.md)|Hilfsmethode, die ein teilweise transparenten Pixel in einer Bitmap Farbe.|  
|[CDrawingManager::SetPixel](../Topic/CDrawingManager::SetPixel.md)|Hilfsmethode, die ein einzelnes Pixel in einer Bitmap der angegebenen Farbe ändert.|  
|[CDrawingManager::SmartMixColors](../Topic/CDrawingManager::SmartMixColors.md)|Kombiniert zwei Farben auf der Grundlage eines gewichtetes relativ.|  
  
## Hinweise  
 Die `CDrawingManager`\-Klasse stellt Funktionen zum Zeichnen von Schatten, von Farbverläufen und von markierten Rechtecken bereit.  Sie führt auch Alphablending aus.  Sie können diese Klasse verwenden, um die Benutzeroberfläche der Anwendung direkt zu ändern.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md)  
  
## Anforderungen  
 **Header:** afxdrawmanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)