---
title: "CRenderTarget Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRenderTarget"
  - "afxrendertarget/CRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRenderTarget-Klasse"
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CRenderTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1RenderTarget".  
  
## Syntax  
  
```  
class CRenderTarget : public CObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](../Topic/CRenderTarget::CRenderTarget.md)|Erstellt ein CRenderTarget\-Objekt.|  
|[CRenderTarget::~CRenderTarget](../Topic/CRenderTarget::~CRenderTarget.md)|Der Destruktor.  Wird aufgerufen, wenn ein Renderingzielobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRenderTarget::Attach](../Topic/CRenderTarget::Attach.md)|Hängt die vorhandene Renderingzielschnittstelle an das Objekt an|  
|[CRenderTarget::BeginDraw](../Topic/CRenderTarget::BeginDraw.md)|Initiiert das Zeichnen auf diesem Renderingziel.|  
|[CRenderTarget::Clear](../Topic/CRenderTarget::Clear.md)|Löscht den Zeichnungsbereich zur angegebenen Farbe.|  
|[CRenderTarget::COLORREF\_TO\_D2DCOLOR](../Topic/CRenderTarget::COLORREF_TO_D2DCOLOR.md)|Konvertiert GDI\-Farbe und Alphawerte in das D2D1\_COLOR\_F\-Objekt.|  
|[CRenderTarget::CreateCompatibleRenderTarget](../Topic/CRenderTarget::CreateCompatibleRenderTarget.md)|Erstellt ein neues Bitmaprenderingziel zur Verwendung für das Offscreen\-Zwischenzeichnen, das mit dem aktuellen Renderingziel kompatibel ist.|  
|[CRenderTarget::Destroy](../Topic/CRenderTarget::Destroy.md)|Löscht eine oder mehrere Ressourcen|  
|[CRenderTarget::Detach](../Topic/CRenderTarget::Detach.md)|Trennt die Renderingzielschnittstelle vom Objekt|  
|[CRenderTarget::DrawBitmap](../Topic/CRenderTarget::DrawBitmap.md)|Zeichnet den vom angegebenen IDWriteTextLayout\-Objekt beschriebenen formatierten Text.|  
|[CRenderTarget::DrawEllipse](../Topic/CRenderTarget::DrawEllipse.md)|Zeichnet die Konturen der angegebenen Ellipse mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawGeometry](../Topic/CRenderTarget::DrawGeometry.md)|Zeichnet die Konturen der angegebenen Geometrie mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawGlyphRun](../Topic/CRenderTarget::DrawGlyphRun.md)|Zeichnet die angegebenen Symbole.|  
|[CRenderTarget::DrawLine](../Topic/CRenderTarget::DrawLine.md)|Zeichnet mit dem angegebenen Strichstil eine Linie zwischen den angegebenen Punkten.|  
|[CRenderTarget::DrawRectangle](../Topic/CRenderTarget::DrawRectangle.md)|Zeichnet die Konturen eines Rechtecks, das die angegebenen Dimensionen und Strichformat hat.|  
|[CRenderTarget::DrawRoundedRectangle](../Topic/CRenderTarget::DrawRoundedRectangle.md)|Zeichnet die Konturen des angegebenen abgerundeten Rechtecks mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawText](../Topic/CRenderTarget::DrawText.md)|Zeichnet den angegebenen Text, der die Formatinformationen verwendet, der von einem IDWriteTextFormat\-Objekt zur Verfügung gestellt wurde.|  
|[CRenderTarget::DrawTextLayout](../Topic/CRenderTarget::DrawTextLayout.md)|Zeichnet den vom angegebenen IDWriteTextLayout\-Objekt beschriebenen formatierten Text.|  
|[CRenderTarget::EndDraw](../Topic/CRenderTarget::EndDraw.md)|Beendet Zeichenvorgänge für das Renderingziel und gibt den aktuellen Fehlerzustand und zugeordnete Tags an.|  
|[CRenderTarget::FillEllipse](../Topic/CRenderTarget::FillEllipse.md)|Zeichnet das Innere der angegebenen Ellipse.|  
|[CRenderTarget::FillGeometry](../Topic/CRenderTarget::FillGeometry.md)|Zeichnet das Innere der angegebenen Geometrie.|  
|[CRenderTarget::FillMesh](../Topic/CRenderTarget::FillMesh.md)|Zeichnet das Innere des angegebenen Gitter.|  
|[CRenderTarget::FillOpacityMask](../Topic/CRenderTarget::FillOpacityMask.md)|Wendet die von der angegebenen Bitmap beschriebene Deckkraftmaske auf einen Pinsel an und verwendet diesen Pinsel, um einen Bereich des Renderingziels zu zeichnen.|  
|[CRenderTarget::FillRectangle](../Topic/CRenderTarget::FillRectangle.md)|Zeichnet das Innere des angegebenen Rechteck.|  
|[CRenderTarget::FillRoundedRectangle](../Topic/CRenderTarget::FillRoundedRectangle.md)|Zeichnet das Innere des angegebenen abgerundeten Rechtecks.|  
|[CRenderTarget::Flush](../Topic/CRenderTarget::Flush.md)|Führt alle ausstehenden Zeichenbefehle aus.|  
|[CRenderTarget::GetAntialiasMode](../Topic/CRenderTarget::GetAntialiasMode.md)|Ruft den aktuellen Antialiasingmodus für Nichttext\-Zeichenvorgänge ab.|  
|[CRenderTarget::GetDpi](../Topic/CRenderTarget::GetDpi.md)|Gibt die Punkte pro Zoll \(DPI\) des Renderingziels zurück|  
|[CRenderTarget::GetMaximumBitmapSize](../Topic/CRenderTarget::GetMaximumBitmapSize.md)|Ruft die maximale Größe, in geräteabhängigen Einheiten \(Pixel\), einer einzelnen vom Renderingziel unterstützten Bitmapdimension ab|  
|[CRenderTarget::GetPixelFormat](../Topic/CRenderTarget::GetPixelFormat.md)|Ruft das Pixelformat und den Alphamodus des Renderingziels ab|  
|[CRenderTarget::GetPixelSize](../Topic/CRenderTarget::GetPixelSize.md)|Gibt die Größe des Renderingziels in Gerätepixel zurück|  
|[CRenderTarget::GetRenderTarget](../Topic/CRenderTarget::GetRenderTarget.md)|Gibt die ID2D1RenderTarget\-Schnittstelle zurück|  
|[CRenderTarget::GetSize](../Topic/CRenderTarget::GetSize.md)|Gibt die Größe des Renderingziels in geräteunabhängigen Pixel zurück|  
|[CRenderTarget::GetTags](../Topic/CRenderTarget::GetTags.md)|Ruft die Bezeichnung für nachfolgende Zeichenvorgänge ab.|  
|[CRenderTarget::GetTextAntialiasMode](../Topic/CRenderTarget::GetTextAntialiasMode.md)|Ruft den aktuellen Antialiasingmodus für Text\- und Symbolzeichenvorgänge ab.|  
|[CRenderTarget::GetTextRenderingParams](../Topic/CRenderTarget::GetTextRenderingParams.md)|Ruft die aktuellen Textrenderoptionen des Renderingziels ab.|  
|[CRenderTarget::GetTransform](../Topic/CRenderTarget::GetTransform.md)|Wendet die angegebene Transformation auf das Renderingziel an und ersetzt die vorhandene Transformation.  Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum auf.|  
|[CRenderTarget::IsSupported](../Topic/CRenderTarget::IsSupported.md)|Gibt an, ob das Renderingziel die angegebenen Eigenschaften unterstützt|  
|[CRenderTarget::IsValid](../Topic/CRenderTarget::IsValid.md)|Überprüft die Ressourcengültigkeit|  
|[CRenderTarget::PopAxisAlignedClip](../Topic/CRenderTarget::PopAxisAlignedClip.md)|Entfernt den letzten an einer Achse ausgerichteten Clip aus dem Renderingziel.  Nachdem diese Methode aufgerufen wurde, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.|  
|[CRenderTarget::PopLayer](../Topic/CRenderTarget::PopLayer.md)|Beendet die Umleitung von Zeichenvorgängen an die Ebene, die vom letzten PushLayer\-Aufruf angegeben wird.|  
|[CRenderTarget::PushAxisAlignedClip](../Topic/CRenderTarget::PushAxisAlignedClip.md)|Entfernt den letzten an einer Achse ausgerichteten Clip aus dem Renderingziel.  Nachdem diese Methode aufgerufen wurde, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.|  
|[CRenderTarget::PushLayer](../Topic/CRenderTarget::PushLayer.md)|Fügt dem Renderingziel die angegebene Ebene hinzu, sodass es alle nachfolgenden Zeichenvorgänge empfängt, bis PopLayer aufgerufen wird.|  
|[CRenderTarget::RestoreDrawingState](../Topic/CRenderTarget::RestoreDrawingState.md)|Legt den Zeichnungszustand des Renderingziels auf den des angegebenen ID2D1DrawingStateBlock fest.|  
|[CRenderTarget::SaveDrawingState](../Topic/CRenderTarget::SaveDrawingState.md)|Speichert den aktuellen Zeichnungszustand im angegebenen ID2D1DrawingStateBlock.|  
|[CRenderTarget::SetAntialiasMode](../Topic/CRenderTarget::SetAntialiasMode.md)|Legt den Antialiasingmodus vom Renderingziel fest.  Der Antialiasingmodus gilt für alle nachfolgenden Zeichenvorgänge, ohne Text\- und Symbolzeichenvorgänge.|  
|[CRenderTarget::SetDpi](../Topic/CRenderTarget::SetDpi.md)|Legt die Punkte pro Zoll \(DPI\) des Renderingziels fest.|  
|[CRenderTarget::SetTags](../Topic/CRenderTarget::SetTags.md)|Gibt eine Bezeichnung für nachfolgende Zeichenvorgänge an.|  
|[CRenderTarget::SetTextAntialiasMode](../Topic/CRenderTarget::SetTextAntialiasMode.md)|Gibt den Antialiasingmodus an, der auf nachfolgenden Text und Symbolzeichenvorgänge angewendet werden soll.|  
|[CRenderTarget::SetTextRenderingParams](../Topic/CRenderTarget::SetTextRenderingParams.md)|Gibt Textrenderingoptionen an, die auf allen nachfolgenden Text und Symbolzeichenvorgänge angewendet werden sollen.|  
|[CRenderTarget::SetTransform](../Topic/CRenderTarget::SetTransform.md)|Überladen.  Wendet die angegebene Transformation auf das Renderingziel an und ersetzt die vorhandene Transformation.  Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum auf.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](../Topic/CRenderTarget::VerifyResource.md)|Überprüft die Gültigkeit des CD2DResource\-Objekts. Das Objekt wird erstellt, wenn es noch nicht vorhanden ist.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget\*](../Topic/CRenderTarget::operator%20ID2D1RenderTarget*.md)|Gibt die ID2D1RenderTarget\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CRenderTarget::m\_lstResources](../Topic/CRenderTarget::m_lstResources.md)|Eine Liste der Zeiger auf CD2DResource\-Objekte.|  
|[CRenderTarget::m\_pRenderTarget](../Topic/CRenderTarget::m_pRenderTarget.md)|Ein Zeiger auf ein ID2D1RenderTarget\-Objekt.|  
|[CRenderTarget::m\_pTextFormatDefault](../Topic/CRenderTarget::m_pTextFormatDefault.md)|Ein Zeiger auf CD2DTextFormat\-Objekt, das ein Standardtextformat enthält.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)